# CDP Control Plane Public API Changelog

## 0.9.29 (2021-03-17)

FEATURES:

* datahub: New `listDatahubDiagnostics` and `cancelDatahubDiagnostics` commands, also added `excludeHosts` and `skipUnresponsiveHosts` parameters to `collectDatahubDiagnostics` command.
* datalake: New `listDatalakeDiagnostics` and `cancelDatalakeDiagnostics` commands, also added `excludeHosts` and `skipUnresponsiveHosts` parameters to `collectDatalakeDiagnostics` command.
* environments: New `listFreeipaDiagnostics` and `cancelFreeipaDiagnostics` commands, also added `excludeHosts` and `skipUnresponsiveHosts` parameters to `collectFreeipaDiagnostics` command.
* environments: New fields added to `CreateAWSEnvironmentRequest`: `endpointAccessGatewayScheme` and `endpointAccessGatewaySubnetIds`. The same fields are also added to the `Network` object.
* ml: New fields in `CreateWorkspaceRequest`: `enableGovernance`, `enableModelMetrics`.

## 0.9.28 (2021-03-03)

IMPROVEMENTS:

* dw: New field in `CreateClusterRequest`: `usePrivateLoadBalancer`. All-private VPC cluster creation is now possible.

## 0.9.27 (2021-03-01)

FEATURES:

* de: New field in `EnableServiceRequest`: `tags`.
* de: New field in `CreateVcRequest`: `runtimeSpotComponent`.
* iam: The `deleteUser` operation no longer requires an entitlement.

IMPROVEMENTS:

* datalake: New field in `DatalakeDetails`, part of `DescribeDatalakeResponse`: `shape`.

NOTES:

* audit: The identityProviderSessionId field in the interactive login audit event is deprecated. It never contained a useful value and will not be populated in the future.
* iam: Many operations are annotated with their form factors. This is related to upcoming improvements to private cloud support, and has no effect on API usage currently.
* iam: Machine user names are no longer permitted to begin with two underscore characters.

## 0.9.26 (2021-02-17)

FEATURES:

* datahub: 2 new operations: `collectCmDiagnostics`, `getCmRoles`.
* datalake: 2 new operations: `collectCmDiagnostics`, `getCmRoles`.

IMPROVEMENTS:

* iam: SAML provider data in responses includes service provider SAML metadata.

NOTES:

* audit: Updated documentation for API audit event response parameters. This has no effect on auditing usage.
* ml: Removed entitlement annotation for service-side auditing. This has no effect on API usage.
* all services: A link to Cloudera's terms of service is provided in API definitions. This is for informational purposes only.

## 0.9.25 (2021-02-03)

FEATURES:

* de: **New service!**

IMPROVEMENTS:

* ml: added nfsVersion option for createWorkspace operation

## 0.9.24 (2021-01-20)

BACKWARD INCOMPATIBILITIES:

* iam: The `getAccount` endpoint is no longer associated with a right. This allows any user to call the endpoint, including those with no roles / rights.

IMPROVEMENTS:

* environments: New field in `StartEnvironmentRequest`: `withDatahubStart`.
* iam: The `samlMetadataDocument` field in `CreateSamlProviderRequest` is now optional, allowing creation of a SAML provider without providing any metadata.

NOTES:

* iam: Replaced the term 'Altus' with 'CDP' in API summaries and descriptions. Some descriptions related to the 'groups' parameter were outdated and updated with additional information. Updated "groups" SAML assertion attribute URN.
* audit, datahub, datalake, environments, iam, odb: Removed entitlement annotations for service-side auditing. This has no effect on API usage.

## 0.9.23 (2021-01-06)

IMPROVEMENTS:

* environments: Added DELETED_BY_PROVIDER, UNHEALTHY, and DELETE_REQUESTED FreeIPA statuses

FEATURES:

* datahub: Added `renewCertificate` operation
* datalake: Added `renewCertificate` operation

## 0.9.22 (2020-12-15)

BACKWARD INCOMPATIBILITIES

* dw: Made `clusterID` field of `DescribeClusterRequest` required; the operation would not work without it previously

IMPROVEMENTS:

* dw: Fixed description of the `ListVwsRequest` object
* dw: Added `autoSuspendTimeoutSeconds`, `enableHA`, `disableAutoSuspend`, `triggerScaleUpDelaySeconds` `triggerScaleDownDelaySeconds` properties to `AutoscalingOptions` object
* dw: Added `enableFeng`, `installViz` properties to `CreateVwRequest` object
* environments: Added `getEnvironmentUserSyncState` operation

## 0.9.21 (2020-12-09)

FEATURES:

* datahub: New autoscaling operations: `createAuditScaleRules`, `updateAutoScaleRules`, `describeAutoScaleRules`, `deleteAuditScaleRules`, `listAutoScaleHistory`
* environments: Added `createPrivateEndpoints` option to environment creation requests
* environments: Added `reportDeploymentLogs` option to environment creation requests

NOTES:

* audit: The service definition is now annotated for service-side auditing. This has no effect on client interaction.

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
