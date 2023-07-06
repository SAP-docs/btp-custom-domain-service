<!-- loio6b9bbbc7216645f09e5c7404fd31cdb2 -->

# IAC Action to Trigger Auditlog Warnings

There is a new IAC action that triggers the auditlog warning task: `start-warning-task`



To manually trigger it without a concourse call:

`iac -d custom-domain-certificates lifecycle start-warning-task`



<a name="loio6b9bbbc7216645f09e5c7404fd31cdb2__section_vzt_xfh_kxb"/>

## Concourse Job for Scheduling the Cloud Foundry Task

Concourse will then run an IAC action that only runs the Cloud Foundry task. The task runs on a daily bases \(every 24 hours\). It calls the IAC action, `start-warning-task`.

