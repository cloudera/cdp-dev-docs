# CDP Control Plane Public API Changelog

## 0.9.20 (2020-11-24)

NOTES:

* iam: The maximum number of records that may be returned from `listAccessKeys` has increased from 100 to 500.
* iam: The maximum number of records that may be returned from `listUsers` has increased from 100 to 500.

## 0.9.19 (2020-11-12)

FEATURES:

* environments: 2 new operations: `collectFreeipaDiagnostics`, `getFreeipaLogDescriptors`.
* datalake: 3 new operations: `collectDatalakeDiagnostics`, `getDatalakeLogDecriptors`, `rotateAutoTlsCertificates`
* datahub: 3 new operations: `collectDatahubDiagnostics`, `getDatahubLogDecriptors`, `rotateAutoTlsCertificates`
* opdb: Creating and listing diagnostic bundles.

## 0.9.18 (2020-10-28)

FEATURES:

* ml: New operations: `getKubeConfig`, `listWorkspaceAccess`.
* odb: **New service!** The new 'opdb' API interacts with Cloudera Operational Database Experience.

IMPROVEMENTS:

* datahub: New fields in `Instance` objects: `privateIp` and `publicIp`.
* datalake: New fields in `Instance` objects: `privateIp` and `publicIp`.
* environments: New fields in `Credential` objects: `awsCredentialProperties` and `azureCredentialProperties`.
* iam: New request field for `setWorkloadPassword` operation: `actorCrn`. This enables setting a workload password for a user other than the caller.

## 0.9.17 (2020-10-13)

BACKWARD INCOMPATIBILITIES:

* datalake: `startDatalake` is deprecated and no longer works. Use `environments.startEnvironment` instead.
* datalake: `stopDatalake` is deprecated and no longer works. Use `environments.stopEnvironment` instead.
* datalake: The `scale` parameter for `createAWSDatalake` and `createAzureDatalake` has changed type from a string to an enum.

NOTES:

* datahub: The service definition is now annotated for service-side auditing. This has no effect on client interaction.
* datalake: The service definition is now annotated for service-side auditing. This has no effect on client interaction.
* environments: The service definition is now annotated for service-side auditing. This has no effect on client interaction.

FEATURES:

* dw: **New service!**
* environments: New operation: `getRepairFreeipaStatus`.
* environments: New audit credential operations: `getAuditCredentialPrerequisites`, `listAuditCredentials`, `setAWSAuditCredential`, `setAzureAuditCredential`.

<!--
Template for a new release

## x.y.z (unreleased, replace with yyyy-MM-dd when released)

BACKWARD INCOMPATIBILITIES:

* service: description, how to compensate

NOTES:

* service: note

FEATURES:

* service: description of major new improvement

IMPROVEMENTS:

* service: description of minor improvement

BUG FIXES:

* service: description of fix
-->
