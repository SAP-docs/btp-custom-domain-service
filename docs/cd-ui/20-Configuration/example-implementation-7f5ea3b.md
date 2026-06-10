<!-- loio7f5ea3b6848e4672ac00686c8126df7f -->

# Example Implementation

This example implementation for macOS or Linux uses CURL and CERTBOT, plus a few further standard shell commands. This is an illustration of the usage.



*Sample Code*

> ### Sample Code:  
> ```
> CBOT() {
>   rm 000*.pem 2>/dev/null
>   rm -rf acme/ 2>/dev/null
>   cat > 0000_csr.pem
>   local ACME_DIR="https://one.digicert.com/mpki/api/v1/acme/v2/directory?action=enroll"
>   local ACME_KID="***********************************************"
>   local ACME_KEY=”*******************************************************************************”
>   certbot -v certonly --manual --preferred-challenges dns --manual-auth-hook true --agree-tos --no-eff-email --register-unsafely-without-email \
>     --csr ./0000_csr.pem \
>     --server $ACME_DIR \
>     --eab-kid "$ACME_KID" \
>     --eab-hmac-key "$ACME_KEY" \
>     --config-dir=./acme/etc \
>     --logs-dir=./acme/logs \
>     --work-dir=./acme/work
>   cat ./0001_chain.pem
>   rm 000*.pem 2>/dev/null
>   rm -rf acme/ 2>/dev/null
> }
> 
> cdrotate() {
>   local IDENTITY GRACEDAYS TOKEN CF_API CF_ORG_NAME CF_ORG_GUID CD_API response body code
>   IDENTITY=$1
>   GRACEDAYS=${2:-30}
>   TOKEN=$(cf oauth-token)
>   CF_API=$(cf t | grep "API endpoint:" | sed -e 's/API endpoint://g' -e 's/ //g' -e 's/api./custom-domains./g')
>   CF_ORG_NAME=$(cf t | grep "org:" | sed -e 's/org://g' -e 's/ //g')
>   CF_ORG_GUID=$(cf org ${CF_ORG_NAME} --guid)
>   CD_API="/api/v3/identities/$1/rotation/rsa3072"
> 
>   response=$(curl -s -w "\n%{http_code}" -H "Authorization: ${TOKEN}" -H "X-CUSTOM-DOMAIN-SERVICE-CF-ORG-ID: ${CF_ORG_GUID}" -H "Content-Type: application/json" ${CF_API}${CD_API}/status -X GET)
>   body=${response%$'\n'*}
>   code=${response##*$'\n'}
>   case $code in
>     200) echo "Rotation possible." ;;
>     400) echo "Bad Request. A parameter is invalid or malformed." ; return 1 ;;
>     404) echo "Not Found. The identity does not exist." ; return 1 ;;
>     422) echo "Unprocessable Entity. The algorithm or SANs does not match the current server certificate configuration." ; return 1 ;;
>     *) echo "ERROR - Rotation status failed with status code $code."; echo $body; return 1 ;;
>   esac
> 
>   # Check if certificate needs rotation based on grace period
>   local daysRemaining=$(echo $body | jq -r '.serverCertificate.chain[0].expirationInfo.daysRemaining // empty')
>   if [[ -n "$daysRemaining" && "$daysRemaining" -ge "$GRACEDAYS" ]]; then
>     echo "Certificate expires in $daysRemaining days, which is >= $GRACEDAYS days grace period. No rotation needed yet."
>     return 0
>   fi
>   echo "Certificate expires in $daysRemaining days (< $GRACEDAYS days grace period). Proceeding with rotation..."
> 
>   while true; do
>     response=$(curl -s -w "\n%{http_code}" -H "Authorization: ${TOKEN}" -H "X-CUSTOM-DOMAIN-SERVICE-CF-ORG-ID: ${CF_ORG_GUID}" -H "Content-Type: application/json" ${CF_API}${CD_API}/initialize -X POST)
>     body=${response%$'\n'*}
>     code=${response##*$'\n'}
>     case $code in
>       202) echo "Rotation pending..." ; sleep 5 ;;
>       201) echo "Rotation initialized successfully." ; break ;;
>       *) echo "ERROR - Rotation initialization failed with status code $code."; echo $body; return 1 ;;
>     esac
>   done
>   csr=$(jq .csr <<< "$body" | sed -e 's/\\n/\n/g' -e 's/^"//g' -e 's/"$//g')
>   certs=$(echo $csr | CBOT)
>   if [[ -z "$certs" ]]; then
>     echo "ERROR - Failed to obtain certificates for rotation."
>     return 1
>   fi
> 
>   response=$(curl -s -w "\n%{http_code}" -H "Authorization: ${TOKEN}" -H "X-CUSTOM-DOMAIN-SERVICE-CF-ORG-ID: ${CF_ORG_GUID}" -H "Content-Type: application/json" ${CF_API}${CD_API}/finalize -X POST --data-binary @- <<< "$certs")
>   body=${response%$'\n'*}
>   code=${response##*$'\n'}
>   case $code in
>     200) echo "Rotation finalized successfully." ;;
>     400) echo "Rotation failed, invalid parameters." ;;
>     *) echo "ERROR - Rotation finalization failed with status code $code."; echo $body ;;
>   esac
> }
> 
> ```

*Sample Run*

> ### Sample Code:  
> ```
> cdrotate e74ce48e-9e25-4b5b-875e-f014638eff3a 50
> 
> Rotation possible.
> Certificate expires in 46 days (< 50 days grace period). Proceeding with rotation...
> Rotation pending...
> Rotation pending...
> Rotation pending...
> Rotation initialized successfully.
> Rotation finalized successfully.
> 
> ```

