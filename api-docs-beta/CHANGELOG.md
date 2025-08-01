# CDP Control Plane Public API Changelog

## 0.9.142 (2025-07-30)
* compute: Add `egressType`, `aksManagedIdentity`, `privateDnsZone`, and `oidcIssuerURL` parameters to the `describeCluster` command response.
* datahub: Add `preferredZones` parameter to the `scaleCluster` command.
* de: Add `sparkOSName` parameter to the `createVc` command.
* environments: Add `loadBalancer` parameter to the `freeipa` parameter of the `environment` parameter. 
* iam: Add `enableUserWorkloadPasswordChangedNotifications` and `disableUserWorkloadPasswordChangedNotifications` commands.
* ml: Add `createFileReplica`, `deleteFileReplica`, and `failOverFileSystem` commands.
* ml: Add `enableFineGrainedAccessControl` parameter to the `createMlServingApp` command.

## 0.9.141 (2025-07-09)
* datacatalog: Add parameters `profilers`, `instanceTypes`, and `maxNodes` to `launchProfilers` command.
* datahub: Add command `migrateSkus`.
* datalake: Add command `migrateSkus`.
* environments: Add parameter `force` to `downscaleFreeipa` command.
* ml: Add parameter `disableObjectStoreCsiDriver` to `createModelRegistry` command.
* ml: Add parameter `disableObjectStoreCsiDriver` to `updateModelRegistry` command.
* ml: Add parameter `enableYunikorn` to `createWorkspace` command.
* ml: Add required parameters `environmentName` and `productType` to `listInstanceTypeConfiguration` command.
* ml: Add required parameters `environmentName` and `productType` to `listRelevantInstances` command.
* ml: Deprecate parameters `region` and `cloudProvider` from `listInstanceTypeConfiguration` command and remove from required parameters.
* ml: Deprecate parameters `region` and `cloudProvider` from `listRelevantInstances` command and remove from required parameters.

## 0.9.140 (2025-06-25)
* ml: Add `describeWorkspaceBackup` command.

## 0.9.139 (2025-06-12)
* cloudprivatelinks: Add parameter `resourceTags` to `create-private-link-endpoint` command.
* datahub: Add parameter `architecture` to `create-aws-cluster` command.
* datalake: Add parameter `customInstanceGroups` to `create-aws-datalake`, `create-aws-gov-cloud-datalake`, `create-azure-datalake` and `create-gcp-datalake` commands.
* dw: Add parameter `logHiveQueries` to `create-vw` and `update-vw` commands.
* dw: Add parameter `resourcePool` to `update-dbc` command.
* opdb: Add parameter `force` to `drop-database` command.

BACKWARD INCOMPATIBILITIES:
* dw: Remove deprecated `resourcePool` parameter from `create-cluster` and `create-private-cluster` commands.
* dw: Remove deprecated `securityContextConstraintName` parameter from `create-private-cluster` command.
* dw: Remove deprecated `dbHue` parameter from `create-private-cluster` command.
* dw: Remove deprecated `dbDas` parameter from `PrivateCloudActivationOptions` object.
* dw: Remove deprecated `dbMetastore` parameter from `create-dbc` command.

## 0.9.138 (2025-05-28)
* datahub: Add property `preferredSubnetIds` to `scaleCluster` command.
* environments: Add property `imageDetails` of the new object `ImageInfo` to `FreeipaDetails` object.

BACKWARD INCOMPATIBILITIES:
* df: Remove `SUSPENDING_FLOW` value from enum `DeploymentState`.
* df: Remove property `clusterUsable` in `ServiceSummary` and `Service` objects.
* dfworkload: Remove `transition-flow`, `download-client-certificate-encoded` and `download-client-private-key-encoded` commands.
* dfworkload: Remove property `clusterSizeName` in `create-deployment` and `update-deployment` commands.
* dfworkload: Remove property `clusterSizeName` in `RpcDeploymentConfiguration` and `RpcImportedDeploymentConfiguration` objects.
* dfworkload: Remove `FAILED_TO_START` and `SUSPENDING_FLOW` values from enum `detailedState` in `DeploymentStatus` object.
* dfworkload: Remove `SUSPENDING_FLOW` value from enum `state` in `DeploymentStatus` object.
* dfworkload: Remove `SUSPEND_FLOW` value from enum `validActions` in `RpcDeployment` object.
* dfworkload: Remove `clusterSize`, `coresPerNode`, `heapSize`, and `memoryLimit` properties in `RpcDeployment` object.


## 0.9.137 (2025-05-14)
* datahub: Add `rotateSecrets` and `listDatahubSecretTypes` commands.
* datalake: Add `rotateSecrets` and `listDatalakeSecretTypes` commands.
* datalake: Add `imageDetails` to `DatalakeDetails` object.
* df: Add `assignToCollection`, `createCollection`, `deleteCollection`, `describeCollection`, `listCollections`, `rotatePassword` and `updateCollection` commands.
* df: Add `collectionCrn` to `ImportFlowDefinitionRequest` object.
* df: Add `collectionCrn` and `collectionName` to `ImportFlowDefinitionResponse` object.
* df: Add `collectionCrn` and `collectionName` to `Flow` and `FlowSummary` objects.
* df: Add `collectionCrn` to `ListFlowDefinitionsRequest` object.
* df: Add `VALKEY` enum value to `DiagnosticsEnvironmentComponent`.
* df: Add `ROTATING_PASSWORD` enum value to `ServiceState`.
* df: Add `upgradeDeploymentsNiFiVersion` to `Service` and `ServiceSummary` objects.
* dfworkload: Rename `InboundConnectionEndpointClientPrivateKeyResponse` to `InboundConnectionEndpointClientCertificatesResponse`.
* dfworkload: Add `AWSNodeStorageProfile`, `AWSNodeStorageProfileMetaData`, `AssetReference` and `AzureNodeStorageProfileMetaData` objects.
* dfworkload: Add `inboundConnectionAuthorizedIpRanges` and `nodeStorage` properties to `CreateDeploymentRequest` object.
* dfworkload: Hide `CUSTOM_AWS`, `CUSTOM_AZURE`, `TEST_SESSION_AWS`, `TEST_SESSION_AZURE` enum values of `nodeStorageProfileName` property in `CreateDeploymentRequest` object.
* dfworkload: Add `sourceParameterGroupId` to `FlowParameter` object.
* dfworkload: Add `inheritedParameterGroups` to `FlowParameterGroup` object.
* dfworkload: Add `authorizedIpRanges` to `InboundConnectionEndpointSummary` object.
* dfworkload: Add `NodeStorage` object.
* dfworkload: Add `CUSTOM_AWS`, `CUSTOM_AZURE`, `TEST_SESSION_AWS`, `TEST_SESSION_AZURE` enum values to `name` property in `NodeStorageProfileMetadata` object.
* dfworkload: Add `azureNodeStorageProfileMetaData` and `awsNodeStorageProfileMetaData` properties to `NodeStorageProfileMetadata` object.
* dfworkload: Add `runtimeStatus`, `nodeStorage`, `targetProcessGroupId` and `inboundConnectionAuthorizedIpRanges` properties to `RpcDeployment` object.
* dfworkload: Add `CUSTOM_AWS`, `CUSTOM_AZURE`, `TEST_SESSION_AWS`, `TEST_SESSION_AZURE` enum values to `nodeStorageProfileName` in `RpcDeploymentConfiguration` object.
* dfworkload: Add `nodeStorage` property to `RpcDeploymentConfiguration` object.
* dfworkload: Add `inboundConnectionAuthorizedIpRanges` and `nodeStorage` properties to `RpcImportedDeploymentConfiguration` object.
* dfworload: Add `VersionedParameterGroupReference` object to `ValidateCustomPythonConfigurationResponse` object.
* environments2: Add `rotateFreeipaSecrets` and `listFreeipaSecretTypes` commands.
* environments2: Add `environmentQuota` to `CreatePrivateEnvironmentRequest` object.
* ml: Deprecate `describeModelRegistry` command.
* ml: Add `getLatestModelRegistryVersion` command.

## 0.9.136 (2025-04-23)
* dw: Add `startDbc` command.
* dw: Add `nonTransparentProxy` property to `createAwsCluster` command.
* dw: Add `nonTransparentProxy` property to `AwsActivationOptions` and `AwsOptionsResponse` objects.
* dw: Add `cdwHueRestorePlans` property to response of `restoreCluster` command.
* dw: Add `forceRefresh` property to `startVw` command.
* dw: Deprecate `restartDbc` and `restartVw` commands.

BACKWARD INCOMPATIBILITIES:
* dw: Remove deprecated `computeInstanceType` property from `createAwsCluster` and `createAzureCluster` commands.
* dw: Remove deprecated `computeInstanceType` property from `AwsActivationOptions` and `AzureActiviationOptions` objects.
* dw: Remove deprecated `computeInstanceType` property from response of `clusterSummary` command.

## 0.9.135 (2025-04-09)
* compute: All compute commands no longer require an entitlement.
* datahub: Add property `clusterName` to `getOperation` command.
* datahub: Deprecate `crn` property in `getOperation` command.
* datalake: Add property `datalakeName` to `getOperation` command.
* datalake: Deprecate `crn` property in `getOperation` command.
* ml: Add property `name` to `WorkspaceInstanceGroup` object.
* ml: Add property `enableEnhancedPerformance` to `CreateWorkspaceRequest` object.
* ml: Remove `clusterCrn` as required parameter in `createMlServingApp` command.
* ml: Add property `ozoneS3Creds` of the new object `MlServingOzoneCreds` to `CreateWorkspaceRequest` object.
* ml: Remove `instanceGroups` as required parameter in `MlServingProvisionK8sRequest` object.
* ml: Add property `loadBalancerIPWhitelists` to `MlServingApp` object.
* ml: Deprecate `isPublic` and `ipAllowlist` properties in `KubernetesCluster` command.
* opdb: Add `architecture` property of the new enum `ArchitectureType` in `DatabaseDetails` object and `createDatabase` command.

BACKWARD INCOMPATIBILITIES:
* environments: Remove deprecated property `networkCidr` from `createAWSEnvironment` command.
* environments: Remove deprecated property `newNetworkParams` from `CreateAzureEnvironment` command.

## 0.9.134 (2025-03-19)
* de: Add `cpuRequests`, `memoryRequests`, and `resourcePool` properties in `ServiceResources` object.
* datahub: Add `restart-cluster-instances` command.
* datalake: Add `restart-datalake-instances` command.

## 0.9.133 (2025-03-13)
* environments: Add `update-tags` command.
* environments: Add `aksPrivateDnsZoneId` property in `update-data-service-resources` command.
* opdb: Add `snapshotId` and `restoreId` properties in `RestoreSnapshot` object.

BACKWARD INCOMPATIBILITIES:
* dw: Remove deprecated property `memorySize` from `DBCUpgrade` and `DBCCreate` commands.

## 0.9.132 (2025-02-19)
* compute: Add a new enum value to the `ComputeClusterType` enum (DedicatedExternal).
* environments: Update summary and description for `updateSshKey`, `updateSubnet`, `updateSecurityAccess` and `updateProxyConfig` commands.

BACKWARD INCOMPATIBILITIES:
* dw: Remove deprecated properties `reservedComputeNodes` and `reservedSharedServicesNodes` from `createCluster`, `createAwsCluster`, `createAzureCluster` and `listClusters` commands.
* environments: Deprecate `networkCidr` property in the request of `createAWSEnvironment` and `createAWSGovCloudEnvironment` commands.

## 0.9.131 (2025-02-05)
* datalake: Add `getOperation` command.
* datahub: Add `getOperation` command.
* datalake: Add `getOperation` command.
* environments: Add `operationId` property environment commands.
* ml: Add properties `resourcePoolName`, `parentResourcePoolName`, `quota`, and `availableQuota` to response of `describeWorkspace` command.
* ml: Add property `resourcePoolConfig` to `createWorkspace` command.

## 0.9.130 (2025-01-23)
* dw: Deprecate `memorySize` property in the `create-dbc` and `update-dbc` commands.
* dw: Deprecate `memorySize` property in the `DbcSummary` object.
* dw: Add `resourceTemplateId` property in the `create-dbc`, and `update-dbc` commands.
* dw: Add `resourceTemplateId` property in the `DbcSummary` object.
* environments: Add new enum value to the `targetAvailabilityType` property of the `upscale-freeipa` command (TWO_NODE_BASED).

BACKWARD INCOMPATIBILITIES:
* dw: Remove deprecated property `downloadOptions` from `create-dbc-diagnostic-data-job` and `create-cluster-diagnostic-data-job` commands.
* dw: Remove deprecated properties `hiveDownloadOptions` and `impalaDownloadOptions` from `create-vw-diagnostic-data-job` command.

## 0.9.129 (2025-01-15)
* compute: Change descriptions of `EngCloudProvider` and `ComputePlatform` enums.
* dfworkload: Add `Error` schema to default responses of `downloadClientCertificateEncoded`, `downloadClientCertificatesEncoded`, `downloadClientPrivateKeyEncoded`, `createInboundConnectionEndpoint`, `deleteInboundConnectionEndpoint`, `describeInboundConnectionEndpoint`, `listInboundConnectionEndpoints`, and `renewCertificates` commands.
* dfworkload: Change description of `type` property in `FlowParameter` object.
* dw: Deprecate `computeInstanceTypes` property in response of `createAwsCluster` and `createAzureCluster` commands.
* dw: Deprecate `computeInstanceTypes` property in `AwsActivationOptions`, `AzureActivationOptions`, and `ClusterSummeryResponse` objects.
* dw: Add new `resetServerSettings` command.
* dw: Add `includeAutomaticBackups` parameter to `listBackups` command.
* environments: Add `started` and `ended` properties to response of `getOperation` command.
* environments: Add `skipOrgPolicyDecisions` and `verifyPermissions` properties to `Credential` object.
* environments: Deprecate `reportDeploymentLogs` parameter in `createAWSEnvironment`, `createAWSGovCloudEnvironment`, `createAzureEnvironment`, `createGCPEnvironment`, `setTelemetryFeatures`, and `setAccountTelemetry` commands.
* environments: Deprecate `reportDeploymentLogs` property in response of `setAccountTelemetry`, `getAccountTelemetry`, and `getAccountTelemetryDefault` commands.
* environments: Deprecate `reportDeploymentLogs` in `Environment` object.

BACKWARD INCOMPATIBILITIES:
* dw: Remove deprecated property `headroom` and `waitQueueSize` from `CreateApplicationResourcesBreakdown` object
* dw: Remove deprecated properties headRoom and waitQueueSize from `UpdateApplicationResourcesBreakdown` and `ApplicationResourcesBreakdown` object
* environments: Rename property `operationType` to `operationName` in the response of `getOperation` command.
* environments: Remove property `progress` from response of `getOperation` command.
* environments: Remove deprecated `userManagedIdentity` parameter from `updateAzureEncryptionResources` command.
* environments: remove deprecated `userManagedIdentity` property from  AzureResourceEncryptionParameters object.

## 0.9.128 (2024-12-11)
* iam: Add `migrateUsersToIdentityProvider` command.
* datahub: Deprecate `rotateSaltPassword` command.
* datalake: Deprecate `rotateSaltPassword` command.
* environments2: Deprecate `rotateSaltPassword` command.

## 0.9.127 (2024-12-06)
* compute: Add `resume-cluster` and `suspend-cluster` commands.
* dw: Deprecate property `downloadOptions` in `CreateClusterDiagnosticDataJobRequest` object.
* dw: the Cluster EOL Support information is available under `list-clusters` and `describe-cluster` command's `productSupport` field.
* dw: the `instanceType` field made available in the `create-vw`, `list-vws`, `describe-vw` commands.
* environments: Add property `operationId` in `InitializeAzureComputeClusterResponse` and `InitializeAWSComputeClusterResponse` objects.
* ml: Remove property `mlVersion` from `CreateWorkspaceRequest` object.
* opdb: Add `create-snapshot`, `delete-snapshot`, `list-restore-snapshots`, `list-snapshots`, and `restore-snapshot` commands.

BACKWARD INCOMPATIBILITIES:
* dw: The `additionalInstanceTypes` field has been removed from the `create-cluster`, `create-aws-cluster`, `create-azure-cluster` commands in favor of the `instanceType` field in `create-vw` command.
* dw: The `templateName` filed has been renamed to `resourceTemplate` in the `create-data-visualization` command.
* dw: The `template` field has been removed in favor of `tShirtSize` in the `create-vw`, `update-vw` commands.

## 0.9.126 (2024-11-13)
* cloudprivatelinks: Add properties `subscriptionId` and `cloudServiceProvider` to `AuthorizePrivateLinkServiceAccessRequest` and `RevokePrivateLinkServiceAccessRequest` objects.
* datahub: Change description of property `type` in  `Recipe`, `RecipeSummary` and `CreateRecipeRequest` objects.
* dw: Deprecate properties `dbDas` and `dbHue` in `PrivateCloudActivationOptions` object.
* dw: Deprecate properties `dbMetastore`, `dbDas` and `dbHue` in `CreateDbcRequest` object.
* dw: Deprecate property `securityContextConstraintName` in `CreatePrivateClusterRequest` and `PrivateCloudActivationOptions` objects.
* environments: Deprecate property `s3GuardTableName` in `CreateAWSEnvironmentRequest`, `CreateAWSGovCloudEnvironmentRequest` and `Environment` object’s `awsDetails` objects.
* environments: Add new command `lastSyncStatus`.
* replicationmanager: Add new properties `clusterCrn`, `requestId`, `message` and `status` to `ActivatePolicyResponse`, `CreatePolicyResponse`, `DeletePolicyResponse` and `SuspendPolicyResponse` objects.

## 0.9.125 (2024-10-30)
* datalake: Add new object 'DiskOptions' to 'StartDatalakeVerticalScalingRequest' & 'startDatalakeVerticalScaling' object.
* datalake: Add new object 'AddDisks', 'ModifyDisks' to 'DiskOptions' object.
* datalake: Add support for adding new additional storages or modifying existing additional storages to 'startDatalakeVerticalScaling' command.
* replicationmanager: Support for HBase replication with create-hbase-policy, update-hbase-policy, continue-hbase-setup, suspend-hbase-policy, activate-hbase-policy, delete-hbase-policy, list-paired-hbase-clusters and verify-hbase-cluster-pair commands.
* replicationmanager: Add get-cluster-config command.
* environments: Add 'azureDetails' to the 'Environment' object.
* environments: Add new commands 'initializeAWSComputeCluster' and 'initializeAzureComputeCluster'.
* environments: Add new properties 'enableComputeCluster' and 'computeClusterConfiguration' to 'CreateAWSEnvironmentRequest' object.
* environments: Add new properties 'enableComputeCluster' and 'computeClusterConfiguration' to 'CreateAzureEnvironmentRequest' object.
* environments: Add new property 'computeClusterEnabled' to 'EnvironmentSummary' object.
* environments: Add new property 'awsComputeClusterConfiguration', 'azureComputeClusterConfiguration' and 'computeClusterEnabled' to 'Environment' object.
* dw: Deprecate property 'downloadOptions' in 'CreateDbcDiagnosticDataJobRequest'.
* dw: Deprecate properties 'hiveDownloadOptions' and 'impalaDownloadOptions' in 'CreateDbcDiagnosticDataJobResponse'.
* dw: Deprecate 'HiveCreateDiagnosticDataDownloadOptions', 'ImpalaCreateDiagnosticDataDownloadOptions', 'DBCCreateDiagnosticDataDownloadOptions' and 'ClusterCreateDiagnosticDataDownloadOptions'.

BACKWARD INCOMPATIBILITIES:
* ml: Remove 'isCrossNsBackup' option from 'BackupDetail' object.

## 0.9.124 (2024-10-16)
* ml: Change descriptions of APIs to reflect naming change from `Cloudera Machine Learning` to `Cloudera AI`.
* ml: Add new command `addInstanceGroups`.
* ml Add new properties `cpu`, `gpu`, and `memory` to `WorkspaceInstanceGroup` object.
* compute: Add new commands `createCluster`, `deleteCluster`, `describeCluster`, `listDeployments`, and `validateCluster`.
* datahub: Add new parameter `diskOptions` to `startClusterVerticalScaling` command.

## 0.9.123 (2024-09-26)
* dw: Deprecate `reservedComputeNodes` and `reservedSharedServicesNodes` fields in some commands.

## 0.9.122 (2024-09-11)
* dw: Add new parameter `impalaExecutorGroupSets` to the autoscale options for the `createVw`, `updateVw`, `listVws`, and `describeVw` commands.
* opdb: Add new parameters `gatewayNodesCount` and `restworkerNodesCount` to `createDatabase` command.
* opdb: Add new parameters `numDesiredRestworkerNodes` and `removeRestworkerNodes` to `updateDatabase` command.
* opdb: Add new properties `gatewayNodesCount` and `restworkerNodesCount` to `DatabaseDetails` object.

## 0.9.121 (2024-09-03)
* de: Add new property `sparkConfigs` to `VcDescription` object.
* de: Add `sparkConfigs` parameter to `createVc` and `updateVc` commands.
* de: Add new commands `upgradeService` and `getUpgradeStatus`.
* de: Add new properties `azureFilesharePrivateDNSZoneId` and `azureDatabasePrivateDNSZoneId` to `enableService` command.
* dw: Remove deprecation tag from `computeInstanceType` parameter in `createAwsCluster` and `createAzureCluster` commands.
* dw: Remove deprecation tag from `computeInstanceType` property in `AwsActivationOptions` and `AzureActivationOptions` objects.
* dw: Remove deprecation tag from `computeInstanceType` field in the response of `clusterSummary` command.
* ml: Add new commands `addInstanceGroupsMlServingApp`, `createMlServingApp`, `deleteInstanceGroupMlServingApp`, `deleteMlServingApp`, `describeMlServingApp`, `getMlServingAppKubeconfig`, `grantMlServingAppAccess`, `listInstanceTypeConfiguration`, `listMlServingAppAccess`, `listMlServingApps`, `listRelevantInstances`, `modifyMlServingApp`, `revokeMlServingAppAccess`, and `upgradeMlServingApp`.
* opdb: Update description of `StorageType` object.
* opdb: Add new command `updateDatabase`.

BACKWARD INCOMPATIBILITIES:
* dw: Remove `Docker` value from enum `registryType` in `CustomRegistryOptions` object.
* dw: Remove `userName`, `password`, and `disableImageVerification` properties from `CustomRegistryOptions` object.
* dw: Remove `upgradeCluster` command.


## 0.9.120 (2024-08-14)
* datalake: Add `rangerCloudAccessAuthorizerRole` parameter to `validate-aws-cloud-storage` command.
* datalake: Add new property `dryRunValidation` to `AdminOperationsBackupRestoreState` object.
* dw: Deprecate property `templateName` in `create-data-visualization` command.
* dw: Deprecate property `template` in `create-vw` command.
* environments: Add new property `created` to `Credential` object.
* cloudprivatelinks: Add new `revoke-private-link-service-access` command.
* cloudprivatelinks: Make `cloudServiceProvider` parameter required in `create-private-link-endpoint` and `delete-private-link-endpoint` commands.

BACKWARD INCOMPATIBILITIES:
* dw: Remove `format` parameter from `ConfigBlockReq` and `ConfigBlockResp` objects.
* cloudprivatelinks: Remove properties `serviceComponents` and `environmentCrn` in `create-private-link-endpoint` and `delete-private-link-endpoint` commands.

## 0.9.119 (2024-07-31)
* datahub/datalake: Add new `rotate-db-certificate` command.
* de: Add new `force` and `includeJobRuns` options to `create-backup` command.
* dw: Add a new command to activate AWS Cluster `create-aws-cluster`.
* dw: Add a new command to activate Azure Cluster `create-azure-cluster`.
* dw: Add a new command to activate a Cluster on Private Cloud `create-private-cluster`.
* dw: Add `privateSQLSubnetName` and `privateDNSZoneSQL` fields to the `create-cluster`, `create-azure-cluster`, `list-clusters` and `describe-cluster` commands.
* dw: Add `aksPodCIDR` field to the `create-cluster`, `create-azure-cluster`, `list-clusters` and `describe-cluster` commands.
* dw: Add deployed cluster `version` field to  `describe-cluster` and `list-clusters` responses.
* dw: Add `useOverlayNetwork` / `enablePrivateLoadBalancer` fields to `describe-cluster` and `list-clusters` response.
* dw: Add `enablePrivateSQL` / `privateDNSZoneAKS` / `enablePrivateAKS` / `userAssignedManagedIdentity` in the Azure options of `describe-cluster` and `list-clusters` response.
* dw: Add a new field `impalaQueryLog` to `create-vw` / `describe-vw` / `list-vws` and `update-vw` command.
* dw: Add a new field `enabledPrivateEKS` to `create-cluster` / `create-aws-cluster` / `describe-cluster` and `list-clusters` command.
* dw: Add a new field `enableStatestoreHighAvailability` to `create-vw` / `update-vw` / `describe-vw` and `list-vws` commands, for Impala.
* dw: Deprecate `additionalInstanceTypes` field in some commands.
* opdb: Remove `id` and `catalog` as required parameters for database `image` details input provided to `create-database` command.

BACKWARD INCOMPATIBILITIES:
* cloudprivatelinks: Remove deprecated `get-private-link-endpoint-status` command.

## 0.9.118 (2024-07-18)
* cloudprivatelinks: Add `cloudServiceProvider` argument to `deletePrivateLinkEndpoint` command.
* datalake: Add new command `cancelRestore`.
* datalake: Add new parameters `skipValidation` and `validationOnly` to `resizeDatalake` command.
* dw: Deprecate `computeInstanceTypes` parameter in `createAwsCluster` and `createAzureCluster` commands.
* dw: Deprecate `computeInstanceTypes` property in response of `clusterSummary` command.
* environments: Add new parameters `imageId` and `allowMajorOsUpgrade` to `upgradeFreeipa` command.
* ml: Add new properties `version` and `endpointPublicAccess` to `ModelRegistry` object.

## 0.9.117 (2024-06-26)
* cloudprivatelinks: Add new property `status` to `AuthorizePrivateLinkServiceAccessResponse` object.
* de: Add support for `Spark 3.5` to `createVc` command.
* compute: Add new properties `isDefault` and `clusterShape` to `ListClusterItems` object.
* compute: Update description of `includeDeleted` in `ListClusters` command.
* dw: Deprecate properties `waitQueueSize` and `headroom` in `CreateApplicationResourcesBreakdown` object.

## 0.9.115 (2024-06-05)
* de: Add new property `allPurposeInstanceGroupDetails` to `ServiceResources` object.
* de: Add new property `sessionTimeout` to `VcDescription` object.
* de: Add new parameters `allPurposeInstanceType`, `allPurposeMinimumInstances`, `allPurposeMaximumInstances`, `allPurposeMinimumSpotInstances`, `allPurposeMaximumSpotInstances`, `allPurposeInitialInstances`, `allPurposeInitialSpotInstances`, and `allPurposeRootVolumeSize` to `enableService` command.
* de: Add new parameters `allPurposeMinimumInstances`, `allPurposeMaximumInstances`, `allPurposeMinimumSpotInstances`, `allPurposeMaximumSpotInstances` to `updateService` command.
* de: Add new parameter `sessionTimeout` to `createVc` command.
* dw: Add new commands `listResourceTemplates`, `createResourceTemplate`, `updateResourceTemplate`, and `deleteResourceTemplate`.
* dw: Add new parameter `resourcePool` to `updateCluster` command.
* dw: Add new parameter `hiveServerHaMode` to `createVw` command.
* dw: Add new parameter `ebsLLAPSpillGB` to `createVw` command.
* dw: Add new parameters `resourcePool` and `hiveServerHaMode` to `updateVw` command.
* dw: Add new property `dbClientCredentials` to `PrivateCloudActivationOptions` object.
* dw: Add new property `resources` to `DbSummary` object.
* dw: Add new property `hiveServerHaMode` to `VwSummary` object.
* dw: Add new property `ebsLLAPSpillGB` to `VwSummary` object.
* environments: Add new command `getFreeipaUpgradeOptions`.
* ml: Add new parameters `whitelistAuthorizedIPRanges` and `authorizedIPRanges` to `createModelRegistry` command.

BACKWARD INCOMPATIBILITIES:
* cloudprivatelinks: Remove `serviceComponents` parameter from `authorizePrivateLinkServiceAccess` command.


## 0.9.114 (2024-05-22)
IMPROVEMENTS:
* environments: Update description of `environmentName` property of `DescribeEnvironmentRequest` object.
* df: Add new enum value to the `state` property of the `DeploymentStatus` object (CHANGING_FLOW_VERSION).
* df: Add new property `EncryptionParameters` to the `Service` object.
* df: Add new parameter `deploymentCrn` to `initiateDeployment` command.
* df: Add new parameter `uuids` to `listDiagnostics` command.
* df: Add new parameter `includeNifiDiagnostics` to `startGetDiagnosticsCollection` command.
* dfworkload: Add `create-custom-python-configuration`, `delete-custom-python-configuration`, `get-custom-python-configuration`, `update-custom-python-configuration`, `validate-custom-python-configuration`, `change-flow-version` and `cancel-change-flow-version` commands.
* dfworkload: Add new enum values to the `detailedState` property of the `DeploymentStatus` object (CHANGING_FLOW_VERSION, FAILED_TO_PREPARE_FOR_CHANGE_FLOW_VERSION, FAILED_TO_CHANGE_FLOW_VERSION, CANCELLING_CHANGE_FLOW_VERSION, FAILED_TO_CANCEL_CHANGE_FLOW_VERSION, PROMETHEUS_APPROACHING_MEMORY_LIMIT).
* dfworkload: Add new enum value to the `state` property of the `DeploymentStatus` object (CHANGING_FLOW_VERSION).
* dfworkload: Add new enum values to the `validActions` property of the `RpcDeployment` object (CHANGE_FLOW_VERSION, RETRY_CHANGE_FLOW_VERSION, CANCEL_CHANGE_FLOW_VERSION)
* dfworkload: Add new parameter `clusterSize` to `create-deployment` and `update-deployment` commands.
* dfworkload: Add new property `CustomClusterSizeLimits` to the `ClusterSize` object.
* dfworkload: Add new enum value for all `clusterSize` and `clusterSizeName` enums (CUSTOM).
* dfworkload: Add new parameter `waitForFlowToStopInMinutes` to stop-flow command.
* dfworkload: Add new properties `customPythonConfigurationCrn` and `clusterSize` to the `RpcImportedDeploymentConfiguration` object.
* dfworkload: deprecated `clusterSizeName` property in `RpcImportedDeploymentConfiguration` object.
* dfworkload: Add new properties `assetConfigurationAvailable` and `clusterSize` to the `RpcDeploymentConfiguration` object.
* dfworkload: deprecated `clusterSizeName` property in `RpcDeploymentConfiguration` object.
* dfworkload: Add new properties `customPythonConfigurationId` and `clusterSizeParams` to the `RpcDeployment` object.
* dfworkload: Add new properties `customPythonConfigurationCrn` and `clusterSize` to the `RpcImportedDeploymentConfiguration` object.
* dw: Add new enum values to the `requiresUpdate` property of `DescribeServerSettingItem` (IMPALA, HIVE, TRINO, CDW_HUE).
* ml: Update description of `ProvisionK8sRequest` object.

BACKWARD INCOMPATIBILITIES:
* datalake: The `datalakeName` parameter of the `CreateAWSDatalakeRequest`, `CreateAWSDatalakeRequest` and `CreateGCPDatalakeRequest` objects have a property `maxLength` change from 100 to 40.

## 0.9.113 (2024-05-07)
IMPROVEMENTS:
* opdb: Add `volumeEncryptions` parameter to `createDatabase` command.
* environments: Replace `userManagedIdentity` with `encryptionUserManagedIdentity` in `createAzureEnvironment` command.

## 0.9.112 (2024-04-25)
IMPROVEMENTS:
* datalake: Add `customInstanceTypes`, `customInstanceDisks` and `customDatabaseComputeStorage` parameters to `resizeDatalake` command.
* datalake: Add `tag` field to the output of `describeDatalake` command.
* de: Add `archiveBasePath` and `archiveLocation` to `Backup` object to display backup archive location.
* dw: Remove deprecated `namespaceName` parameter from `createBackup` command.
* dw: Deprecate `podConfigName` from `AutoscalingOptions` object.
* opdb: Add `rootVolumeSize` parameter to `createDatabase` command.


## 0.9.111 (2024-04-10)
IMPROVEMENTS:
* environments: Add `updateCustomDockerRegistry` command.
* environments: Add `instanceId` parameter to `getFreeipaStatus` command.
* datalake: Add `enableRangerRms` parameter to `createAWSDatalake` command.
* dw: deprecated `delegationUsername` and `delegationPassword` options for `privateCloudOptions` parameter for `createCluster` command.
* datahub: Add `getVmTypes` command.
* de: Add `fullAccessUsers`, `fullAccessGroups`, `viewOnlyUsers`, and `viewOnlyGroups` parameters to `updateVc` command.
* ml: Add new `upgradeModelRegistry` and `rollbackModelRegistryUpgrade` command.


## 0.9.109 (2024-03-27)
IMPROVEMENTS:
* datalake: Add `scaleHorizontally` command.
* dw: Add `hiveKerberosJdbc`, `impalaFengKerberosJdbc`, and `fengKerberosImpalaShell` fields in response of `describeVw` and `listVws` commands.
* dfworkload: deprecated `download-client-certificate-encoded`, use `download-client-certificates-encoded` instead.
* dfworkload: deprecated `download-client-private-key-encoded`, use `download-client-certificates-encoded` instead.
* dfworkload: `name` parameter of `clusterSize` object is now an enum.
* dfworkload: deprecated `clusterSizeName` parameter of `create-deployment` command.
* dfworkload: deprecated `clusterSize`, `coresPerNode`, and `memoryLimit` parameters of command responses that include `RpcDeployment` object.
* dfworkload: deprecated `clusterSizeName` parameter of command responses that include `RpcDeploymentConfiguration` object.
* dfworkload: deprecated `clusterSizeName` parameter of `update-deployment` command.
* de: Add `fullAccessUsers`, `fullAccessGroups`, `viewOnlyUsers`, and `viewOnlyGroups` parameters to `createVc` command.

BACKWARD INCOMPATIBILITIES:
* dfworkload: The `coresPerNode` parameter of the `clusterSize` object has a type change from integer to double.


## 0.9.108 (2024-03-13)
IMPROVEMENTS:
* datalake: Add `rollingUpgradeEnabled` parameter to `upgrade-cluster` request.
* datalake: Add `totalPredicatedDurationInMinutes` field in the response of `backup-datalake-status` command.
* datalake: Add `predicatedDurationInMinutes` field to `BackupRestoreOperationStatus` object.
* de: Add `backupLocation` field to `ServiceDescription` object.
* de: Add `create-backup`, `cancel-backup`, `delete-backup`, `describe-backup`, `get-backup-logs`, `get-service-init-logs`, `list-backups` and `restore-service` commands.
* dw: Add `memorySize` parameter to `create-dbc` and `update-dbc` commands.
* dw: Add `memorySize` field to `DbcSummary` object.
* environments: Add `encryptionAtHost` parameter to `create-azure-environment-request` command.
* ml: `provisionK8sRequest` parameter is no longer required in `create-workspace` command.

BACKWARD INCOMPATIBILITIES:
* dw: Remove `keepImageVersion` parameter from `rebuild-dbc` and `rebuild-vw` requests.
* ml: Remove `createWorkspacePayload` parameter from the `create-model-registry` command.


## 0.9.107 (2024-02-28)
IMPROVEMENTS:
* iam: Add `OPDB` to `WorkloadName` enum of `generateWorkloadAuthToken` command.
* dw: Update description of `backupCluster` command.
* ml: Add `backupCrn` parameter to `createModelRegistry` command.
* ml: Make `provisionK8sRequest` parameter required in `createWorkspace` command.
* opdb: Add `attachedStorageForWorkers`, `customUserTags`, `disableJwtAuth`, `disableKerberos`, `disableMultiAz`, `enableGrafana`, `enableRegionCanary`, `numEdgeNodes` and `subnetId` parameters to the `create-database` command.



## 0.9.106 (2024-02-12)
IMPROVEMENTS:
* cloudprivatelinks: Add `authorizePrivateLinkServiceAccess`, `createPrivateLinkEndpoint`, `deletePrivateLinkEndpoint`, `getPrivateLinkEndpointStatus`, `listPrivateLinkEndpointStatuses`, `listPrivateLinkServicesForRegion` APIs.
* datahub: Add `recipes` field to `InstanceGroup` object.
* datahub: Add `flexibleServerDelegatedSubnetId` parameter to the `create-azure-cluster` command.
* datalake: Add `recipes` field to `InstanceGroup` object.
* datalake: Add `flexibleServerDelegatedSubnetId` parameter to `create-azure-datalake` command.



## 0.9.105 (2024-01-19)
IMPROVEMENTS:
* environments: Add `update-azure-availability-zones` command.
* environments: Add `availabilityZones` parameter to the `create-azure-environment` command.
* environments: Add `multiAz` parameter to the `Environment` object.
* datahub: Add `availabilityZones` parameter to the `create-azure-cluster` command.
* df: Add `create-flow-version-tag`, `delete-flow-version-tag`, `list-flow-definition-versions`, and `list-flow-version-tags` commands.
* dfworkload: Add `export-deployment`, `import-deployment`, `list-deployment-archives`, `download-client-certificates-encoded` commands.
* opdb: Add `recipes` and `image` parameters to the `create-database` command.

## 0.9.104 (2024-01-04)
Maintenance update


## 0.9.103 (2023-12-13)

IMPROVEMENTS:
* datahub: Add `multiAz` and `databaseType` parameters to `create-azure-cluster` command.
* datalake: Add `multiAz` and `databaseType` parameters to `create-azure-datalake` command.
* environments: Add new `update-azure-database-resources` command.
* environments: Add `multiAz` and `flexibleServerSubnetIds` parameters to `create-azure-environment` command.
* environments: Add `instanceCountByGroup` field on `FreeipaDetails` object.


## 0.9.102 (2023-11-29)

IMPROVEMENTS:
* ml: Add `create-model-registry`, `delete-model-registry`, `describe-model-registry`, `get-model-registry-kubeconfig`, `grant-model-registry-access` commands.
* compute: Add support for `DedicatedExternal` clusterType.
* dh: Add new `environmentName` field on `ClusterSummary` object
* dfworkload: Introduce export/import deployment related endpoints from the CLI `list-deployment-archives`, `export-deployment` and `import-deployment`.

BACKWARD INCOMPATIBILITIES:
* dfworkload: Add new enum values for the `detailedState` property of the `DeploymentStatus` object.
* dfworkload: Add new enum value for the `state` property of the `DeploymentStatus` object.
* dfworkload: Add new enum values for the `validActions` property of the `RpcDeployment` object.


## 0.9.101 (2023-11-09)

IMPROVEMENTS:
* environments: Add `update-data-service-resources` command.
* environments: Add `dataServices` parameter for the `create-azure-environment` command.
* opdb: Add `autoScalingParameters` parameter for `create-database` command.
* dw: Add `resourcePool` parameter for `create-cluster`, `create-vw` commands.
* dw: Add `resourcePool` parameter for the `describe-cluster`, `list-data-visualizations`, `list-dbcs`, `list-vws`, `create-data-visualization` commands.
* dw: Add `namespaceNames` parameter for `create-backup` command.
* dw: Add `dedicatedExecutorNodes` parameter for the `PrivateCloudActivationOptions` object.
* df: Add `cancel-delete-project`, `create-project`, `delete-project`, `describe-project`, `list-project-filter-options`, `list-projects`, and `update-project` commands.
* dw: Deprecate `namespaceName` parameter from the `create-backup` command.
* dw: Deprecate `hiveAuthenticationMode` parameter from the `create-vw`, and `update-vw` commands.
* dw: Deprecate `hiveAuthenticationMode` paramter from the `VwSummary` object.


## 0.9.100 (2023-10-25)

IMPROVEMENTS:
* datalake: Add `multiAz` option for resizing a datalake.
* datalake: Add `ENTERPRISE` as a target size in `resize-datalake` command.
* environments: Add `get-azure-image-terms-policy` and `update-azure-image-terms-policy` commands.
* environments: Add new parameter `endpointAccessGatewaySubnetIds` to `update-subnet` command.
* opdb: Add new parameter `scaleType` and `storageType` to `create-database` command.

## 0.9.99 (2023-10-11)

IMPROVEMENTS:
* environments: Support GCP for `get-audit-credential-prerequisites` command.
* de: Support more spark versions for `create-vc` command.
* datalake: Added `ENTERPRISE` to `DatalakeScaleType` enum of `create-gcp-datalake` command.
* dw: The `list-events` command has been introduced to track entity and workflow events.
* dw: In the `update-vw` command the Virtual Warehouse size can ben updated with the `template` / `nodeCount` parameters.
* dw: The `restore-cluster` command has two new fields, `action` and `message`, these proved tell the restore-plan for clusters.
* df: Deprecated `SUSPENDING_FLOW` enum value of `DeploymentState`.
* df: `create-deployment` now allows `node-storage-profile-name` optional parameter to be specified with possible values (STANDARD_AWS, STANDARD_AZURE, PERFORMANCE_AWS or PERFORMANCE_AZURE).
* df: Added new enum values to `DeploymentState` (STOPPING_FLOW, FLOW_STOPPED, SUSPENDING, RESUMING).
* dfworkload: Added new property `nodeStorageProfileName` (string) for `DeploymentConfiguration` object.
* dfworkload: Added new property `valueSet` (boolean) for the `FlowParameter` object.
* dfworkload: New endpoints and models `start-flow`, `stop-flow`, `resume-deployment`, `suspend-deployment`, `restart-deployment`.
* dfworkload: Deprecated `transition-flow`, updated description to indicate to refer to `start-flow` and `stop-flow`.
* dfworkload: Deprecated `FAILED_TO_START` and `SUSPENDING_FLOW` enum values for `detailedState` in the `DeploymentStatus` object.
* dfworkload: Deprecated `SUSPENDING_FLOW` enum value for `state` in the `DeploymentStatus` object.
* dfworkload: Deprecated `SUSPEND_FLOW` enum value for `validActions` in the `RpcDeployment` object.
* dfworkload: Added new enum values to the `validActions` property of `RpcDeployment` (STOP_FLOW, EXPORT, SUSPEND, RESUME, DOWNLOAD_LOG).
* dfworkload: `nodeStorageProfileName` is now a required for `CreateDeploymentRequest`.
* dfworkload: Added new enum values for the `detailedState` property of the `DeploymentStatus` object (FAILED_TO_STOP_FLOW, FAILED_TO_START_FLOW, FLOW_STOPPED, STOPPING_FLOW, SUSPENDING, RESUMING, SUSPENDED, FAILED_TO_SUSPEND, FAILED_TO_RESUME, EXCESSIVE_OFFLOAD_TIME).
* dfworkload: Added new enum values for the `state` property of the `DeploymentStatus` object (STOPPING_FLOW, FLOW_STOPPED, SUSPENDING, RESUMING, SUSPENDED).
* dfworkload: `InboundConnectionEndpointClientCertificateRequest` object now requires `crn` (string) `environmentCrn` (string) parameters. It also removed `id` as a parameter (it was deprecated previously).
* dfworkload: `InboundConnectionEndpointClientPrivateKeyRequest` object now requires `crn` (string) and `environmentCrn` (string) parameters. It also removed `id` as a parameter (it was deprecated previously).

## 0.9.98 (2023-09-27)

IMPROVEMENTS:
* consumption: **New Service** to visualize details about Cloudera credits consumption.
* de: Add `networkOutboundType` field to `enableService` command.
* iam: Add `status` field to `machineUser` object.
* environments: The `encryptionKey` field for `createGCPEnvironment` command no longer requires an entitlement.

## 0.9.97 (2023-09-14)

IMPROVEMENTS:
* environments: Add new commands `set-endpoint-access-gateway`, `update-subnet`, `upgrade-freeipa`, `retry-freeipa`, `list-connected-data-services`, `get-operation`, `set-gcp-audit-credential`, `update-ssh-key`, `update-security-access`, `get-gov-cloud-credential-prerequisites`, `create-aws-gov-cloud-environment`, `create-aws-gov-cloud-credential`, `get-gov-cloud-audit-credential-prerequisites`, and `set-aws-gov-cloud-audit-credential`.
* datalake: Add new command `create-aws-gov-cloud-datalake`.
* datalake: Add new target version `VERSION_14` for the `start-database-upgrade` command.
* datahub: Add new commands `start-instances`, `stop-instances`, and `create-aws-gov-cloud-cluster`.
* dw: Add new commands `backup-cluster` and `restore-cluster`.
* dw: Add `reservedComputeNodes` and `reservedSharedServicesNodes` options to the `create-cluster` command for over provisioning.
* dw: Add `reservedComputeNodes`, `reservedSharedServicesNodes` and `externalBuckets` fields to the `list-clusters` and `describe-clusters` commands.
* dw: Add `enablePrivateSQL`, `privateDNSZoneAKS`, and `enablePrivateAks` options in the `create-cluster` command for creating private AKS clusters.
* dw: Add `operationId` and `hueRestorePlans` fields to `RestoreClusterResponse` object.
* dw: Add `readyCoordinatorReplicas`, `numOfCores`, `memoryCapacity`, and `nodeCount` fields for the `list-vws` and `describe-vw` commands.
* dw: Add `userGroups`, and `adminGroups` fields to the `list-data-visualizations` and `describe-data-visualization` commands.

BACKWARD INCOMPATIBILITIES:
* dw: Remove `privateSubnetIds` and `publicSubnetIds` fields from the `awsOptions` paramter for the `create-cluster` command.

## 0.9.96 (2023-08-30)

IMPROVEMENTS:
* environments: Add new commands `update-proxy-config`, `validate-aws-cloud-storage`, and `validate-azure-cloud-storage`.
* environments: Add `instanceType` field to `AWSFreeIpaCreationRequest` object.
* environments: Add `instanceType` field to `AzureFreeIpaCreationRequest` object.
* environments: Add `instanceType` field to `GCPFreeIpaCreationRequest` object.
* datalake: Add new commands `describe-database-server`, `validate-aws-cloud-storage`, and `validate-azure-cloud-storage`.
* ml: Add `privateCluster` field to `CreateWorkspaceRequest` object.

## 0.9.95 (2023-08-24)

IMPROVEMENTS:
* de: Add `networkOutboundType` to `ServiceDescription` object. Currently `udr` is the only supported.
* de: Update description of `enablePrivateNetwork` field.
* * dw: Add `impalaKerberosJdbc`, `fengImpalaShell`, and `kerberosImpalaShell` endpoints.
* dw: Add `hiveAuthenticationMode` field to `CreateVwRequest` object.
* iam: Add new APIs to set and retrieve default IdP used during Workload initiated SSO. These APIs are - `/iam/getDefaultIdentityProvider` and `/iam/setDefaultIdentityProvider`.

BACKWARD INCOMPATIBILITIES:
* dw: Deprecate `createDbc` command.
* iam: Mark `samlProviderName` field as required for `DescribeSamlProviderRequest` and `DeleteSamlProviderRequest`.

## 0.9.94 (2023-08-09)

IMPROVEMENTS:
* datahub: Add `os` parameter to cluster creation commands.
* datalake: Add `os` parameter to cluster creation commands.
* environments: Add `os` parameter to cluster and FreeIPA creation commands.
* dw: Deprecated `privateSubnetIds` and `publicSubnetIds` parameters for `createCluster` command.
* ml: Deprecated `workspaceCrn` parameter for `getLogs` and `getAuditEvents` commands.

## 0.9.93 (2023-07-28)

IMPROVEMENTS:
* environments: Add `instances` parameter to `downscale-freeipa` command.
* environments: Add `endpointAccessGatewayScheme` parameter to `create-azure-environment` and `create-gcp-environment` commands.
* environments: Set `enableTunnel` parameter value to `true` as default in the `create-aws-environment`, `create-azure-environment` and `create-gcp-environment` commands.
* df: Add `flowMetricsScalingEnabled` field to `Deployment` object.
* df: Add `userDefinedRouting`, `podCidr`, and `serviceCidr` parameters to `enable-service` command.
* df: Add `userDefinedRouting`, `podCidr`, and `serviceCidr` fields to `service` object.
* ml: Add `isRestored` field to `WorkspaceSummary` object.
* ml: Add `isRestored` field to `Workspace` object.

## 0.9.92 (2023-07-13)

IMPROVEMENTS:
* df: Add new command `upgrade-service`.
* df: Deprecated `clusterUsable` parameter in `ServiceSummary` and `Service` objects.
* df: Add `skipPreflightChecks` parameter to `enable-service` and `update-service` commands.
* dfworkload: Add `flowMetricsScalingEnabled` parameter to `create-deployment`and `update-deployment` commands.
* dfworkload: Add `flowMetricsScalingEnabled` fields to `DeploymentConfiguration` and `RpcDeployment` objects.
* datahub: `id` and `catalogName` fields as no longer required in `ImageRequest` object.
* datalake: `id` field is no longer required in `ImageRequest` object.
* replicationmanager: Add new command `get-command-status`.
* environments: Add `endpointAccessGatewaySubnetIds` parameter to `create-azure-environment` and `create-gcp-environment` commands.
* environments: `targetAvailabilityType` parameter is no longer required by `downgrade-freeipa-request` command.

BACKWARD INCOMPATIBILITIES:
* dw: Remove `enablePrivateSql`, `privateDNSZoneAKS` and `enablePrivateAks` fields from the `AzureActivationOptions` object used by `create-cluster` command.

## 0.9.91 (2023-06-28)

IMPROVEMENTS:
* environments: Add `availabilityZones` parameter to `create-gcp-environment` command.
* ml: Add `mlVersion` parameter to `create-workspace` and `restore-workspace` commands.
* replicationmanager: Add `collect-diagnostic-bundle`, `download-diagnostic-bundle`, `create-abfs-credential`, `create-aws-credential` and `delete-credential` commands.

## 0.9.90 (2023-06-21)

IMPROVEMENTS:
* dw: Add `usePublicWorkerNode` parameter to `create-cluster` command.
* datahub: Add `instanceGroup.availabilityZones` parameter to `create-aws-cluster` command.
* datahub: Add `attachedVolumes`, `availabilityZone`, `clouderaManagerServer`, `instanceGroup`, `instanceVmType`, `rackId`, `sshPort`, `statusReason`, and `subnetId` fields to `Instance` object.
* datahub: Add `instanceGroups.subnetIds` parameter to `create-aws-cluster`, `create-azure-cluster` and `create-gcp-cluster` commands.
* datalake: Add `availabilityZones` field to `InstanceGroup` object.
* datalake: Add `attachedVolumes`, `availabilityZone`, `clouderaManagerServer`, `instanceVmType`, `rackId`, and `subnetId` fields to `Instance` object.
* datalake: Add `multiAz` parameter to `create-aws-datalake` command.
* environments: Add `instances` field to `FreeipaDetails` object.
* environments: `image.catalog` and `image.id` parameters are no longer required by `create-aws-environment` and `create-azure-environment` commands.

## 0.9.89 (2023-06-14)
* de: Add `previousVersionDeployed` to `ServiceDescription` object returned in `describeService`, `vcTier` to `VcDescription` object returned in `describeVc`, `deployPreviousVersion` to `EnableServiceRequest` and `vcTier` to `CreateVcRequest`.
* datalake: Add `skipBackupValidation` to `UpgradeDatalakeRequest`.
* environments: Add new command `updateOrchestratorState`.
* compute: Add `includeDeleted` to `ListClustersRequest`, `values` to `Chart`, `overrides` to `Deployment`, `overrides` to `History`.

## 0.9.88 (2023-06-01)

IMPROVEMENTS:
* dw: Add new commands `backup-cluster` and `restore-cluster`.
* datahub: Add new commands `list-scaling-activities` and `describe-scaling-activity`.
* datahub: Add `javaVersion` parameter to `create-aws-cluster`, `create-azure-cluster` and `create-gcp-cluster` commands.
* datalake: Add `javaVersion` parameter to `create-aws-datalake`, `create-azure-datalake` and `create-gcp-datalake` commands.

BACKWARD INCOMPATIBILITIES:
* dw: Remove deprecated `enableUptimeSLA` field from `azureOptions` in the `create-cluster` command.

## 0.9.87 (2023-05-18)

IMPROVEMENTS:
* dw: Enable `replicaStatus` field in private cloud.
* datahub: Add `instanceType` field to `Instance` object.
* datalake: Add `discoveryFQDN`, `instanceStatus`, `statusReason`, `sshPort`, `instanceGroup`, `instanceTypeVal` to `Instance` object.
* de: Support `SPARK3_3` in field `sparkVersion` of `CreateVcRequest` command.

## 0.9.86 (2023-05-05)

IMPROVEMENTS:
* dw: Add new commands `describeDbcConfig`, `updateDbcConfig`, `describeVwConfig`, and `updateVwConfig`
* dw: Add parameters `whitelistK8sClusterAccessIpCIDRs` and `whitelistWorkloadAccessIpCIDRs` to `createCluster` command. The new parameters replace `whitelistIpCIDRs` on Public Cloud deployments.
* dw: Add new parameters `workerSubnetIds` and `lbSubnetIds` to `createCluster` command for AWS clusters.
* dw: Add new parameter `userAssignedManagedIdentity` to `createCluster` command for Azure clusters.
* dw: Add new parameter `observabilityConfig` to `updateCluster` command.
* dw: Add new parameter `platformJwtAuth` to `createVw` command.
* dw: `enableUptimeSLA` has been deprecated for `createCluster` command for Azure clusters.
* opdb: `environment` and `database` parameters are no longer required for `upgradeDatabase` command.
* ml: `newWorkspaceParameters` and `backupCrn` parameters are no longer required for `restoreWorkspace` command.

BACKWARD INCOMPATIBILITIES:
* dw: the `pause-vw` command has been removed in favour of `suspend-vw`
* dw: Removed `dockerBridgeCidr` and `customId` parameter from `createCluster` command for Azure clusters.

## 0.9.85 (2023-04-20)

IMPROVEMENTS:
* datalake: Add `skipBackupValidation` parameter to `upgrade-datalake` command.
* environments: Add `enableOutboundLoadBalancer` parameter to `create-azure-environment` command.
* environments: Add new command `attach-freeIpa-recipes` to attach recipes to FreeIPA.
* environments: Add new command `detach-freeIpa-recipes` to detach recipes from FreeIPA.

## 0.9.84 (2023-04-06)

IMPROVEMENTS:
* df: Add new command `get-flow-version` for getting flow definition.
* df: Add new command `get-kubeconfig` for getting kubernetes configuration for an environment.
* df: Add new command `list-diagnostics` to list diagnostics.
* df: Add new command `start-get-diagnostics-collection` to get start diagnostics bundle creation and upload.
* df: Add `cfmNifiVersion` parameter to `describe-deployment` command.
* df: Add `destination`, `collectionScope`, and `environmentComponents` parameters to `list-diagnostics` and `start-get-diagnostics-collection` commands.
* df: Add `availableK8sVersionUpgrade` parameter to `describe-service`, `enable-service`, `update-service`, and `upgrade-service` commands.
* df: Add parameter `instanceType` to `enable-service` command.
* dfworkload: Add new command `delete-custom-nar-configuration` to delete orphaned custom NAR configuration.
* dfworkload: Add `crn` parameter to `inbound-connection-endpoint-client-certificate` and `inbound-connection-endpoint-client-private-key` commands.
* computeadmin: Added `values` parameter to `Deployment` object returned in `upgrade-deployment`, `describe-deployment`, and `list-deployments` commands.
* computeadmin: Added `verbose` parameter to `list-deployments` command.

BACKWARD INCOMPATIBILITIES:
* df: Add value `IMPORTING_FLOW` to `state` parameter enum to `list-deployments` and `describe-deployments` commands.
* dfworkload: Add `FAILED_TO_IMPORT`, `IMPORTING_FLOW`, `METERING_OFFLINE`, `CERTIFICATE_RENEWED`, and `NOT_HEALTHY` to `status` parameter enum to the `renew-inbound-connection-endpoint-certificate` command.
* dfworkload: Remove deprecated `id` parameter from `describe-inbound-connection-endpoint` and make `crn` a required parameter for the `describe-inbound-connection-endpoint` command.
* dfworkload: Mark `id` parameter as deprecated and not required for `inbound-connection-endpoint-client-certificate` and `inbound-connection-endpoint-client-private-key` commands.
* dfworkload: Remove deprecated `deploymentId` and `id` parameters from `list-inbound-connection-endpoints` and `describe-inbound-connection-endpoint` commands.

## 0.9.83 (2023-03-23)

IMPROVEMENTS:

* datalakedr: Create `skipAtlasIndexes` as an option on datalake backup/restore.
* iam: Add new command `describeSamlProvider` for describing a SAML provider.

BACKWARD INCOMPATIBILITIES:

* compute: Deprecate the `overrides` field in the response of `describeDeployment` command.
* dw: Remove the `tenantStorageLocation` field from the request of `createDbc` command.


## 0.9.82 (2023-03-09)

IMPROVEMENTS:

* drscp: Add new state `TERMINATING` to backup, recovery, and data recovery service jobs.
* ml: Add new parameter `skipValidation` to `deleteBackup` command.

BACKWARD INCOMPATIBILITIES:

* datahub: Change paramater `loadBasdePolicy` to `loadBasedPolicy` auto scale command responses.


## 0.9.81 (2023-02-22)

IMPROVEMENTS:

* dw: Add new command `create-cluster-diagnostic-data-job` for creating diagnostic bundles for clusters.
* dw: Add new command `list-cluster-diagnostic-data-job` for listing diagnostic jobs for clusters.
* dw: Add new command `describe-cluster-diagnostic-data-job` to get details about a given cluster diagnostic jobs.
* dw: Add new command `delete-cluster-diagnostic-data-job` to remove a finished cluster diagnostic jobs.
* dw: Add new command `upgrade-cluster` to upgrade a cluster to the latest version.
* dw: Add new command `rebuild-dbc` to rebuild a Database Catalog.
* dw: Add new command `rebuild-vw` to rebuild a Virtual Warehouse.
* dw: Add new command `suspend-dbc` to suspend a given Database Catalog.
* dw: Add `availabilityZone` parameter to the `create-vw` / `describe-vw` / `list-vws` commands.
* dw: Add `replicaStatus` parameter to the `describe-vw` / `list-vws` commands.
* dw: Add a new top-level `impalaOptions` parameter to the `create-vw` / `update-vw` / `describe-vw` / `list-vws` commands where the Impala spill to S3 setting can be adjusted.
* dw: Remove `vmGenerationType` parameter for Azure clusters in the `create-cluster` command.
* dw: Mark `pause-vw` command as deprecated in favor of the new `suspend-vw` command.
* dw: Mark `enableUnifiedAnalytics` parameter in the Autoscaling object of the `create-vw` / `update-vw` / `describe-vw` / `list-vws` commands.
* dw: The `enableUnifiedAnalytics` flag became a top-level flag of the `create-vw` / `update-vw` / `describe-vw` / `list-vws` commands.
* dw: The Impala High-availability setting got a new dedicated object in the `create-vw` / `update-vw` / `describe-vw` / `list-vws` commands.

## 0.9.80 (2023-02-09)

IMPROVEMENTS:

* Minor bug fixes

## 0.9.79 (2023-02-02)

IMPROVEMENTS:

* dfworkload: Add `flowDesignerId` and `customNarConfigurationId` parameters to `createDeployment` command.
* dw: Add `createBackup`, `deleteBackup`, `describeBackup`, `restoreBackup`, `describeRestore`, `listBackupEntities`, `listBackups`, `listRestores` and `getLogs` commands.
* environments: Add `aksPrivateDnsZoneId` parameter to `createAzureEnvironment` command.
* environments: Add `updateAzureCredential` command.
* environments: Add `authenticationType` and `certificate` parameters to `createAzureCredential` command.
* ml: Add `cdswMigrationMode` and `outboundTypes` parameters to `createWorkspace` command.

## 0.9.78 (2023-01-18)

IMPROVEMENTS:

* environments: `subscriptionId` and `tenantId` parameters no longer required in `createAzureCredential` command to support Azure certificate based authorization.
* iam: Add `unlockUserInControlPlane`, `unlockMachineUserInControlPlane`, and `updateUser` commands.
* ml: Add `requestWorkflowCancellation` command.

## 0.9.77 (2023-01-04)

IMPROVEMENTS:

* compute: Add `totalClusters` and `totalPages` parameters to `listClusters` response.
* compute: `maximum` parameter for `listClusters` command increased from 100 to 500.
* drscp: Add `backupPhase` and `backupJobState` parameters to `listBackups` command.
* drscp: Add `restorePhase` and `restoreJobState` parameters to `listRestores` command.
* ml: Add `instanceType` parameter to `modifyClusterInstanceGroup` command.
* environments: `applicationId` and `secretKey` parameters no longer required in `createAzureCredential` command to support Azure certificate based authorization.
* environments: Add `securityGroupIDsForKnox` and `defaultSecurityGroupIDs` parameters to `createAzureEnvironment` and `createAWSEnvironment` commands.
* datahub: Add `updateOrchestratorState` command.
* datalake: Add `updateOrchestratorState` command.

## 0.9.76 (2022-12-16)

IMPROVEMENTS:

* datalake: Add `skipValidation` and `validationOnly` parameters to  `backupDatalake` and `restoreDatalake` commands.
* drscp: `listItems` command is now `listBackupEntities`.
* dw: Add `describeServerSetting` and `updateServerSetting` commands.
* datalake: Add `skipRangerHmsMetadata`, `skipAtlasMetadata`, and `skipRangerAudits` parameters to `upgradeDatalake` command.

## 0.9.75 (2022-11-29)

IMPROVEMENTS:

* datahub: Add `start-cluster-vertical-scaling` command.
* datalake: Add `start-datalake-vertical-scaling` command.
* drscp: Add `create-backup`, `restore-backup`, `delete-backup`, `describe-backup`, `describe-restore`, `list-backups` and `list-restores` commands.
* dw: Add `describe-allowed-instance-types`, `list-dbc-events` and `list-vw-events` commands.
* dw: Add `computeInstanceTypes` and `additionalInstanceTypes` parameter to `create-cluster` command.
* compute: Add `workloads`, `status`, `clusterType`, `creationTime`, `deletionTime`, `updateTime`, `clusterStateVersion`, `clusterOwner`, `region`, `message`, `account`, `availableUpgrades`, `imageCatalog`, `storage` to the `list-clusters` command.
* environments: Add `start-free-ipa-vertical-scaling` command.
* ml: Add `install-workspace` command.

## 0.9.74 (2022-11-10)

IMPROVEMENTS:

* iam: Constrain `type` parameter to an enum type in `create-user-access-key`, `create-machine-user-acess-key`, `update-access-key`, `get-access-key` and `list-access-keys` commands.
* datahub, datalake: Parameter `targetVersion` is no longer required for `start-database-upgrade` command.
* datalake: Add `precheckStoragePermission` and `rangerAuditCollectionValidation` parameters to `backup-datalake` and `restore-datalake` commands.
* dw: Remove `enableUDR` parameter in `create-cluster` and `cluster-summary` commands.
* ml: Add `resume-workspace` and `suspend-workspace` commands.
* ml: Add `deleteInstanceGroup` command.
* ml: Add `skipValidation` and `subnetsForLoadBalancers` parameters to `create-workspace`  command.
* ml: Add `upgradeState`, `nfsVersion` and `isPrivate` parameters to `describe-workspace` and `list-workspaces` commands.
* ml: Add `subnets`, `subnetsForLoadBalancers` and `clusterID` parameters to `describe-workspace` command.

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
* environments: Add `multiAz` parameter to `create-aws-environment` and `create-aws-gov-cloud-environment` commands.

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
