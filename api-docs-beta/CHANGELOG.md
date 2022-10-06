# CDP Control Plane Public API Changelog

## 0.9.73 (2022-10-06)

IMPROVEMENTS:

* environment: Add `rotate-salt-password` command to rotate SaltStack user password on FreeIPA instances. 
* datalake: Add `rotate-salt-password` command to rotate SaltStack user password on DataLake instances.
* datahub: Add `rotate-salt-password` command to rotate SaltStack user password on Data Hub instances.

## 0.9.72 (2022-10-05)

IMPROVEMENTS:

* dfworkload: Add `renew-certificates` operation for Inbound Connection Endpoints.
* ml: Add `restoreJobTimeoutMinutes` parameter to `restore-workspace` command.
* ml: Add `backupJobTimeoutMinutes` and `skipValidation` parameters to `backup-workspace` command.
* datahub: Add `start-database-upgrade` command to upgrade the database of the Data Hub cluster.
* datalake: Add `start-database-upgrade` command to upgrade the database of the Data Lake cluster.

BACKWARD INCOMPATIBILITIES:

* dfworkload: Deprecate usage of internal IDs in favor of CRNs in Inbound Connection Endpoints. Internal IDs no longer required for `delete-inbound-connection-endpoint` and `describe-inbound-connection-endpoint` commands.

## 0.9.71 (2022-09-28)

IMPROVEMENTS:

* compute: **New Service** for Cloudera Compute API.
* compute: Add `describe-deployment` command to get details of a deployment in the cluster.
* compute: Add `list-clusters` command to list the clusters of an environment.
* compute: Add `upgrade-deployment` command to upgrade a deployment in the cluster.
* dw: Add `databaseBackupRetentionPeriod` parameter to `create-cluster` command.
* dw: Add `customRegistryOptions` parameter to `create-cluster` command.
* dw: Add `customId` parameter to `create-cluster` command.
* dw: Add `customSubdomain` parameter to `create-cluster` command.
* dw: Add `nodeRoleCDWManagedPolicyArn` property in `awsOptions` parameter of `create-cluster` command.
* dw: Add `enableSpotInstances` property in `awsOptions` parameter of `create-cluster` command.
* dw: Add `enableSpotInstances` property as a response to `describe-cluster`/`list-clusters` commands.
* dw: Add `reducedPermissionMode` property in `awsOptions` parameter of `create-cluster` command and also in the response of `describe-cluster`/`list-clusters` commands.
* dw: Add `nodeCount` parameter to `create-vw` command.
* dw: Add `queryIsolationOptions` parameter to `create-vw` command.
* dw: Add `logAnalyticsWorkspaceId` as property of `azureOptions` in response to `describe-cluster`/`list-clusters` commands.
* dw: Add `name` property as a response to `describe-cluster`/`list-clusters` commands.
* dw: Add `configId` property as a response to `describe-vw`/`list-vws` commands.
* dw: Add `cdhVersion` property as a response to `describe-vw`/`list-vws` commands.
* dw: Add `endpoints` property as a response to `describe-vw`/`list-vws` commands. Its sub-properties are `hiveJdbc`, `impalaJdbc`, `impalaFENGJdbc`, `impalaShell`, `hue`, `das`.
* environments: Add `update-aws-disk-encryption-parameters` command to update the AWS encryption key ARN for an environment.

## 0.9.70 (2022-09-19)

IMPROVEMENTS:

* datahub: Add command `prepare-cluster-upgrade`.
* datalake: Add command `prepare-datalake-upgrade`.
* datalake: Make `backupLocation` parameter required in `backup-datalake` command.
* dfworkload: Add values `UNASSIGNED`, `ASSIGNED`, `PROVISIONING_CERTIFICATES`, `RENEWING_CERTIFICATES`, `READY` and `FAILED` to `state` parameter enum to `create-inbound-connection-endpoint`, `describe-inbound-connection-endpoint` and `describe-inbound-connection-endpoint`.

## 0.9.69 (2022-09-01)

IMPROVEMENTS:

* Cloudera CDP Java SDK is upgraded to use Java 11 as the compiler, it also needs Java 11 as the runtime.
* de: Add `storageAccountName`, `resourceGroup` and `azureFilesFQDN` parameters to `enable-service` command.

## 0.9.68 (2022-08-18)

IMPROVEMENTS:

* ml: Add `backup-workspace`, `delete-backup`, `list-workspace-backups`, `restore-workspace` and `migrate-cdsw-workspace` commands.

## 0.9.67 (2022-08-15)

* dw: Add `enableStorageRoles` and `outboundType` parameter to `create-cluster` command.
* dw: Remove deprecated `customEcrRepository` parameter from `create-cluster` command.
* dw: Deprecate `enableUDR` parameter in `create-cluster` command.
* dw: Add `environmentCrn`, `clusterId`, `name`, `status` and `cloudPlatform` parameters to `list-clusters` command.
* dw: Add `disableAutoSuspend`, `autoSuspendTimeoutSecond`, `enableUnifiedAnalytics`, `hiveScaleWaitTimeSeconds`, `hiveDesiredFreeCapacity`, `impalaHighAvailabilityMode`, `impalaScaleUpDelaySeconds`, `impalaScaleDownDelaySeconds`, `impalaEnableShutdownOfCoordinator`, `impalaShutdownOfCoordinatorDelaySeconds`, `impalaNumOfActiveCoordinators` and `podConfigName` parameters to `autoscaling-options-create` command.
* dw: Add `disableAutoSuspend`, `autoSuspendTimeoutSecond`, `hiveScaleWaitTimeSeconds`, `hiveDesiredFreeCapacity`, `impalaScaleUpDelaySeconds`, `impalaScaleDownDelaySeconds`, `impalaShutdownOfCoordinatorDelaySeconds` and `impalaNumOfActiveCoordinators` parameters to `autoscaling-options-update` command.
* dw: Add `autoscalingOptions`, `queryIsolationOptions`, `capacitor`, `viz`, `autoscalingOptions` and `queryIsolationOptions` parameters to `list-vws` and `describe-vw` commands.
* dw: Add `dbcId`, `compactor` and `viz` parameters to `list-vws` command.
* dw: Add `awsOptions` and `azureOptions` parameters to `describe-cluster` and `list-clusters` commands.
* dw: Deprecate `enableUDR` parameter in `describe-cluster` and `list-cluster` commands.
* dw: Add `awsOptions`, `azureOptions` and `enableStorageRoles` parameters in `describe-cluster` and `list-cluster` commands.
* dw: Change default value of `force` parameter to `false` in `delete-cluster` command.

## 0.9.66 (2022-08-03)

IMPROVEMENTS:

* datalake: Add `instanceGroupNames` and `instances` parameters to `renew-certificate` and `repair-datalake` commands.
* dfworkload: Add `download-client-certificate-encoded`, `download-client-private-key-encoded`, `create-inbound-connection-endpoint`, `delete-inbound-connection-endpoint`, `describe-inbound-connection-endpoint` and `list-inbound-connection-endpoints` commands.
* dfworkload: Add `STOPPED`, `SDX_OTPUT_CHANGED` and `METRICS_UNAVAILABLE` status values to `cancel-nifi-version-update`, `create-deployment`, `terminate-deployment`, `transition-flow` and `update-nifi-version` commands.


## 0.9.65 (2022-07-12)

IMPROVEMENTS:

* datahub: Deprecate `clusterDefinitionName`, `environmentName` and `clusterTemplateName` parameters from the `create-aws-cluster` command.

## 0.9.64 (2022-06-28)

IMPROVEMENTS
* dw: Add API to run diagnostic jobs over virtual warehouses.
* dw: Add API to change autoscaling configuration for virtual warehouses.
* dw: Deprecate the `customEcrRepository` attribute in favor of `CustomRegistryOptions`.
* environments: Add a new property `workloadAnalytics` to `Environment` definition.
* environments: Add `downscale-freeipa` and `upscale-freeipa` commands to change the number of FreeIPA nodes hence FreeIPA availability type.
* iam: Add a new property `clouderaSSOAllLoginEnabled` to `Account` definition.

## 0.9.63 (2022-06-17)

IMPROVEMENTS:

* environments: `setPassword` command is deprecated. Use `set-workload-password` in iam instead.
* datahub: Add `listClusterLifecycleEvents` command.

## 0.9.62 (2022-06-10)

IMPROVEMENTS:

* df: Add `activeInfoAlertCount` parameter to `describe-deployment`, `describe-service`, `enable-service`, `list-deployments`, `list-services` and `update-service` commands.
* df: Add `k8sServerVersion` parameter to `describe-service`, `enable-service` and `update-service` commands.
* dw: Change default for `maxClusters` to `10` in `create-vw` command.
* dw: Add `dbDas` and `dbHue` parameters to `create-cluster` command.
* dw: Add `create-data-visualization`, `get-data-visualization-upgrade`, `list-data-visualizations`, `delete-data-visualization`, `describe-data-visualization` and `update-data-visualization` commands.
* environments: Add `databasePrivateDnsZoneId` parameter to `create-aws-gov-cloud-environment`, `create-aws-environment`, `create-azure-environment`, `create-gcp-environment`, `create-private-environment`, `update-aws-disk-encryption-parameters`, `update-azure-encryption-resources`, `update-security-access`, `update-ssh-key` and `update-subnet` commands.
* iam: Add `generateWorkloadUsernameByEmail`, `enableScim` parameters to `create-saml-provider`, `list-saml-providers`, `describe-saml-provider` and `update-saml-provider` commands.
* iam: Add `create-scim-access-token`, `list-scim-access-tokens` and `delete-scim-access-token` commands.
* iam: Add `enableScim` and `scimUrl` parameters to `create-saml-provider`, `list-saml-providers`, `describe-saml-provider` and `update-saml-provider` commands.
* imagecatalog: Make `provider` and `imageType` parameters required for `find-default-image` command.
* opdb: Add `describe-upgrade-database` and `upgrade-database` commands.
* replicationmanager: Add `mapReduceService` and `logPath` paramters to `create-policy` and `create-hbase-policy` commands.
* replicationmanager: Add `sourceClusterCrn` and `targetClsterCrn` parameters to `list-policies` command.


## 0.9.61 (2022-05-16)

IMPROVEMENTS:

* datahub: Add `subnetIds`, `multiAz` parameters to `create-aws-cluster` command.
* datahub: Add `create-`, `delete-`, `describe-` and `list-custom-configurations` commands.
* datalake: Add `multiAz` parameter to `create-*-datalake` and `list-datalakes` commands.
* de: Add `privateClusterEnabled`, `publicEndpointEnabled`, `workloadAnalyticsEnabled` and `ssdUsed` parameters to `describe-service` and `enable-service` commands.
* de: Add `enablePrivateNetwork` parameter to `enable-service` command.
* dw: Add `privateCloudOptions` parameter to `create-cluster` command.
* dw: Add `dbMetastore`, `dbDas` and `dbHue` parameters to `create-dbc` command.
* environments2: Add `multiAz` parameter to `create-aws-environment` and `create-aws-gov-cloud-environment` commands.

## 0.9.60 (2022-04-27)

IMPROVEMENTS:

* Marked `collect-*-diagnostics`, `describe-*`, `get-*`, `list-*`, `summarize-*` and `validate-*` commands as non-mutating.
* clusterconnectivity: Commented deprecation for `certificate` parameter in `list-agents`, `register-agent` and `rotate-agent-access-key` commands.
* compute: Remove mutating designation from `create-resource-pool`, `delete-resource-pool` and `update-resource-pool` commands.
* datahub: Commented deprecations for `renew-certificate` and `rotate-auto-tls-certificates` commands.
* datalake: Add `operationStates`, `runtimeVersion` parameter to `backup-datalake`, `backup-datalake-status`, `restore-datalake` and `restore-datalake-status` commands.
* datalake: Commented deprecations for `renew-certificate`, `start-datalake`, `stop-datalake`, `rotate-auto-tls-certificates` commands.
* datalake: Add `resize-datalake` command.
* dw: Add `awsOptions` and `azureOptions` public parameters to `create-cluster` command.
* dw: Made `id`, `format` and `content` mandatory in `config.{commonConfigs|applicationConfigs}.configBlocks` for `create-vw-request` and `update-vw` commands.
* dwx: Add `privateCloudOptions` for `activate-environment-by-crn` command.
* iam: Add `workloadPasswordDetails` parameter to `create-machine-user` and `list-machine-users` command.
* opdb: Mark `fetch-database-metrics` command as non-mutating.
* sample: Mark `test-enum-deserialization` and `download-file` commands as non-mutating.
* servicediscovery: Commented deprecations for `describe-warehouse` and `list-warehouses-for-env` commands.

## 0.9.59 (2022-04-08)

IMPROVEMENTS:

* datalake: Add `create-aws-gov-cloud-data-lake` command to create a data lake on AWS cloud.
* de: Add `loadbalancerAllowlist` parameter to `describe-service` and `enable-service` commands.
* dw: Add `get-upgrade-vw-versions` and `list-latest-versions` command to list product versions.
* dw: Add `add-user`, `delete-user` and `list-users` commands to manage users.
* dw: Add `renew-certificates`, `update-cluster` and `health-check` commands to manage CDW warehouses.
* dw: Add `start-vw`, `pause-vw`, `restart-vw` and `upgrade-vw` commands to manage virtual warehouses.
* dw: Add `restart-dbc`, `get-upgrade-dbc-versions` and `upgrade-dbc` commands to manage database catalogs.
* dw: Add `enableSpotInstances`, `enableUDR`, `enablePrivateSQL`, `privateDNSZoneAKS`, `enablePrivateAks`, and `enableUptimeSLA` parameters to `create-cluster` command.
* dw: Made `update-ssh-key` available in the public form factor.
* environments: Add `check-database-connectivity` command for private form factor.
* environments: Add `create-aws-gov-cloud-environment` command to create an AWS GovCloud environment. FreeIPA server will be automatically provisioned.
* environments: Add `create-aws-gov-cloud-credential` command to create an AWS credential for GovCloud.
* environments: Add `govCloud` parameter to commands `set-azure-audit-credential`, `set-aws-audit-credential`, `list-audit-credentials`, `create-azure-credential`, `create-gcp-credential`, `create-aws-credential`.
* imagecatalog: Fixed spelling, grammar and sentence structure in the command descriptions.

## 0.9.58 (2022-03-23)

IMPROVEMENTS:

* datahub: Add `sync-component-versions-from-cm` command.
* datahub: Add `enableLoadBalancer` parameter to `create-aws-cluster` and `create-azure-cluster` commands.
* datahub: Add `includeNginxReport` and `includeSarOutput` parameters in `collect-datahub-diagnostics` command.
* datalake: Add `renew-public-certificate` and `rotate-private-certificates` commands, which supersede now deprecated `renew-certificate` and `rotate-auto-tls-certificates` commands.
* datalake: Add `includeNginxReport` and `includeSarOutput` parameters to `collect-datalake-diagnostics` command.
* datalake: Add `skipRangerHmsMetadata`, `skipAtlasMetadata`, and `skipRangerAudits` parameters to `backup-datalake` and `restore-datalake` commands.
* datalake: Add `recipes` parameter to `create-aws-datalake`, `create-gcp-datalake`, and `create-azure-datalake` commands.
* datalake: Deprecate `includeDatabase` of the `restore-datalake` command.
* dm: Deprecate `operationId` field of the `update-service` command response.
* ml: Add `modify-cluster-security`, `modify-cluster-instance-group` and `modify-workspace-load-balancer` commands.
* ml: Remove `useLegacyHelm2` parameter from `create-workspace` and `restore-workspace` commands.

## 0.9.57 (2022-03-02)

IMPROVEMENTS:

* environments: Add `encryptionKeyArn` parameter to `create-aws-environment` command.
* environments: Add `encryptionKey` parameter to `create-gcp-environment` command.
* environments: Add `update-azure-encryption-resources` command.
* datalake: Add `replace-recipes` command for datalake clusters.
* datalake: Add `skipBackup` parameter to `upgrade-datalake` command.

## 0.9.56 (2022-02-16)

IMPROVEMENTS:

* datalake: Add new command `recover-datalake` to recover datalake to the original version after a failed upgrade.
* de: Add `smtpConfig` parameter to `create-vc` command to specify SMTP configurations during virtual cluster creation.

## 0.9.55 (2022-02-02)

IMPROVEMENTS:

* iam: Add new commands `set-workload-password-policy`, `unset-workload-password-policy` and `unset-workload-password-min-lifetime` to configure workload password complexity policies. The existing workload password complexity configurations can be viewed by the `get-account` command.
* audit: Add `filteredInvalidGroups` property to audit `InteraciveLoginEvent`. The field represents a list of invalid groups that were filtered during the IdP initiated interactive login event.
* audit: Add enhanced query options for `list-events` command.
* de: Make DE commands available in CDP Private Cloud form factor.

## 0.9.54 (2022-01-19)

IMPROVEMENTS:

* imagecatalog: **New service!** for managing custom VM images.
* datahub: Add `set-catalog` command.
* datalake: Add `set-catalog` command.
* environments: Add `set-catalog` command.
* environments: Add `create-service-endpoints` parameter to `create-aws-environment` command.
* datalake: Add `sync-component-versions-from-cm` command to sync component versions from CM after a failed upgrade.
* de: Add `update-service` command to update Cloudera Data Engineering (CDE) Service.
* iam: Add `generate-workload-auth-token` command for Private Cloud form factor.

## 0.9.53 (2022-01-05)

IMPROVEMENTS:

* datalake: Add `enable-ranger-raz` parameter to `create-aws-datalake`, `create-azure-datalake` command and the response of `describe-datalake` command.

BACKWARD INCOMPATIBILITIES:

* datalake: Make `cloud-provider-configuration` parameter required for `create-gcp-datalake` command. This matches what we expect for similar APIs for AWS and Azure.

## 0.9.52 (2021-12-16)

IMPROVEMENTS:

* opdb: Add more enumeration values to cloud-break status: `UNREACHABLE`, `NODE_FAILURE`, `RECOVERY_IN_PROGRESS`, `RECOVERY_REQUESTED` and `RECOVERY_FAILED`.
* de: Users can specify subnets during service creation by the new `subnets` parameter of `enable-service` command.
* environments: Add Azure encryption parameters `encryption-key-url` and `encryption-key-resource-group-name` to `create-azure-environment` command.
* datahub: Add new command `replace-recipes` to replace recipes for the given instance groups.
* audit: Add new commands `batch-events-for-archiving`, `get-batch-events-for-archiving-status`, `list-events-in-archive-batch`, `list-outstanding-archive-batches` and `mark-archive-batches-as-successful` to support pull-based archiving.

## 0.9.51 (2021-12-01)

IMPROVEMENTS:

* replicationmanager: Make `path` parameter optional when creating Hive replications.
* datalake: Make `backup-id` parameter required when the `backup-location-override` parameter is used in `restore-datalake` command.

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
