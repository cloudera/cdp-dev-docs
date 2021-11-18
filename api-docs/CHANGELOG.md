# CDP Control Plane Public API Changelog

## 0.9.50 (2021-11-17)

IMPROVEMENTS:

* datahub: Add new `upgrade-cluster` command to upgrade the OS or data platform on a datahub cluster.
* environments: Add new `free-ipa` parameter to `create-gcp-environment` command for GCP FreeIPA HA.

## 0.9.49 (2021-11-03)

IMPROVEMENTS:

* environments: Add new `check-environment-connectivity` and `check-kubernetes-connectivity` commands for checking connectivity for Private Cloud environments.
* replicationmanager: **New service!**

## 0.9.48 (2021-10-20)

IMPROVEMENTS:

* environments: New `create-private-subnets` parameter for `create-aws-environment` command.

## 0.9.47 (2021-10-08)

IMPROVEMENTS:

* iam: Add new `generate-workload-auth-token` command to generate an access token which is required for sending requests to workload APIs.

## 0.9.46 (2021-10-05)

IMPROVEMENTS:

* datalake: Users can skip closing database connections during data lake backup.
* de: Users can specify ACL during virtual cluster creation and update.
* de: Users can specify spark version while creating a cluster.
* dw: Add `isDefault`, `tenantStorageRole` and `tenantStorageLocation` in `create-dbc` command.

## 0.9.45 (2021-09-29)

IMPROVEMENTS:

* ml: Add `whitelistAuthorizedIPRanges` and `authorizedIPRanges` in `create-workspace` command.
* environments: Add `create-private-environment`, `get-environment-setting` and `set-environment-setting` command to Private Cloud.

## 0.9.44 (2021-09-13)

IMPROVEMENTS:

* dw: Enable configuration of `customEcrRepository`, `customAmiId` in AwsActivationOptions.
* dw: Enable configuration of `vmGenerationType`, `logAnalyticsWorkspaceId` and `dockerBridgeCidr` in AzureActivationOptions.
* datalake: Make mandatory parameter `instanceGroupName` as optional.

## 0.9.42 (2021-08-18)

IMPROVEMENTS:

* datahub: Expanded access to `GetClusterServiceStatus` and `GetClusterHostStatus`

FEATURES:

* dw: New `imageVersion` parameter for `CreateVwRequest` and `CreateDbcRequest`.

## 0.9.41 (2021-08-04)

FEATURES:

* datacatalog: Add High Availability (HA) option for datacatalog profilers.

## 0.9.40 (2021-07-21)

FEATURES:

* environments: Add granular cloud provider policy response in credential prerequisites for AWS.
* datahub: Add cluster certificate expiration state in list datahubs operation's response.
* datalake: Add cluster certificate expiration state in list datalakes operation's response.

## 0.9.39 (2021-07-09)

FEATURES:

* ml: Revert the name change of `healthInfoLists` property in 0.9.38.

## 0.9.38 (2021-07-07)

BACKWARD INCOMPATIBILITIES:

* ml: The `healthInfoLists` property is renamed to `healthInfos` in `listWorkspaces` command response.

FEATURES:

* environments: New `noProxyHosts` parameter for ProxyConfig and Environment related commands.
* datacatalog: New `datacatalog` command, users can execute operations such as launching profilers in DataCatalog.

## 0.9.37 (2021-06-23)

FEATURES:

* de: New `removeDeleted` parameter for `listServices` command.
* de: New `skipValidation` parameter for `enableService` command.
* opdb: New values for `StatusType` enumeration.
* environments: New `deleteAuditCredential` command.

## 0.9.36 (2021-06-09)

BACKWARD INCOMPATIBILITIES:

* iam: The `setWorkloadPasswordPolicy` operation is removed, with no replacement at this time.

FEATURES:

* dw: New operation `updateSshKey` for updating the SSH key of a cluster.

## 0.9.35 (2021-05-26)

FEATURES:

* audit: New `getArchivingStatus` and `listRecentArchiveRuns` commands.
* environments: Enable public endpoint access gateway for existing environments.
* compute: The service is available for use with CDP Private Cloud.
* dw: The service is available for use with CDP Private Cloud.

IMPROVEMENTS:

* audit: The `archiveAuditEvents` command is now asynchronous and returns a new `taskId` field that can be used to track status.

## 0.9.34 (2021-05-12)

NOTES:

* audit: Documentation on the `ArchiveBatch` object now explicitly defines a negative event count as meaning that the count is not available.

FEATURES:

* environments: New field in log storage requests: `backupStorageLocationBase`; new field in environments: `backupStorage` with provider-specific details.

IMPROVEMENTS:

* dw: New `tags` field in `CreateVwRequest` allows for specifying tags for resources.
* dw: New `describeKubeconfig` operation for clusters returns a kubeconfig with full access to the cluster.
* datalake: New field in `DatalakeDetails`: `cloudStorageBaseLocation`.

## 0.9.33 (2021-04-29)

NOTES:

* audit: The model object `ArchiveAuditEventsBatchResponse` is renamed to `ArchiveBatch`. This should not affect client usage, and older client code may continue to use the prior name.

FEATURES:

* datalake: New fields in `UpdateDatalakeRequest`: `imageId`, `runtime`, `lockComponents`, `dryRun`, `showAvailableImages`, `showLatestAvailableImagePerRuntime`.
* datalake: New fields in `UpdateDatalakeResponse`: `current`, `upgradeCandidates`, `reason`.
* datalake: New field in `CreateAWSDatalakeRequest`, `CreateAzureDatalakeRequest`, and `CreateGCPDatalakeRequest`: `image`.

IMPROVEMENTS:

* datahub: The `rootVolumeSize` field in `InstanceGroupRequest` is now optional.

## 0.9.32 (2021-04-28)

FEATURES:

* ml: The service is available for use with CDP Private Cloud.
* environments: enabled custom image catalogs for FreeIPA

NOTES:

* dw: EnableSSO set in config option for VW creates SSO enabled cluster.
* dw: LdapGroups configuration support.

BUG FIXES:

* dw: Enable SSO and LDAPGroups Support from CLI.

## 0.9.31 (2021-04-13)

BACKWARD INCOMPATIBILITIES:

* de: The `provisionerid` field in `EnableServiceRequest` has been removed, as it was never supported. There is no replacement.

IMPROVEMENTS:

* datalake: New field in `RestoreDatalakeRequest`: `backupLocationOverride`.

NOTES:

* audit: The listEvents operation has additional annotations pertaining to the paging of results. This does not change API usage, but can allow clients to automatically accumulate several pages of data to satisfy a single overall query.
* datalake: An unnecessary empty set of properties in the definition of UpgradeDatalakeResponse was removed. This has no effect on API usage.

## 0.9.30 (2021-03-30)

FEATURES:

* environments: GCP APIs are added: `createGCPEnvironment` and `createGCPCredential`
* datalake: GCP APIs are added: `createGCPCluster` and
* datahub: GCP APIs are added: `createGCPCluster` and

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
* audit, datahub, datalake, environments, iam, opdb: Removed entitlement annotations for service-side auditing. This has no effect on API usage.

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
* opdb: **New service!** The new 'opdb' API interacts with Cloudera Operational Database Experience.

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
