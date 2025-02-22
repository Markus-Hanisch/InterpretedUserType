# InterpretedUserType table

| InterpretedUserType | Possible Description |
|------- | -------------------- |
|AADConnectDisabledOnlineActiveDirectoryDisabledUser||
|AADConnectDisabledOnlineActiveDirectoryDisabledUserPendingDeletionFromAD||
|AADConnectDisabledOnlineSfBUserWithTeamsLicensePendingDeletionFromAD||
|AADConnectDisabledOnlineTeamsUserPendingDeletionFromAD||
|AADConnectDisabledOnlineTeamsUser||
|AADConnectDisabledOnlineUserNotLicensedForServicePendingDeletionFromAD||
|AADConnectDisabledOnlineUserNotLicensedForService||
|AADConnectEnabledOnlineActiveDirectoryDisabledUserPendingAttributeRemovalFromAD||
|AADConnectEnabledOnlineActiveDirectoryDisabledUser||
|AADConnectEnabledOnlineSfBUserWithTeamsLicense||
|AADConnectEnabledOnlineSfBUserWithTeamsLicenseWithMCOValidationError||
|AADConnectEnabledOnlineTeamsOnlyUserNotLicensedForServiceInPDLPendingAttributeRemovalFromAD||
|AADConnectEnabledOnlineSfBUser||
|AADConnectEnabledOnlineTeamsUserNeedsProvisioningToAD||
|AADConnectEnabledOnlineTeamsUserWithMCOValidationError||
|AADConnectEnabledOnlineTeamsUser||
|AADConnectEnabledOnlineUserNotLicensedForServiceNeedsProvisioningToAD||
|AADConnectEnabledOnlineUserNotLicensedForServiceNotInPDL||
|AADConnectEnabledOnlineUserNotLicensedForServicePendingAttributeRemovalFromAD||
|AADConnectEnabledOnlineUserNotLicensedForService||
|AADConnectEnabledSfBUserWithTeamsLicenseNeedsProvisioningToAD||
|DirSyncDisabledDisabledUser| User account disabled in SfB online and disabled in local AD, has a sipAddress attribute online, RegistrarPool has a value.|
|DirSyncDisabledNoService| User account disabled in SfB online and does not have a sipAddress attribute online, RegistrarPool empty, OnPremHostingProvider shows sipfed.online.lync.com.|
|DirSyncDisabledSfBUser| User account disabled in SfB online and has a sipAddress attribute online, also, has a RegistrarPool value and OnPremHostingProvider is empty.|
|DirSyncDisabledUser| User account disabled in SfB online and disabled in local AD, does not have a RegistrarPool value.|
|DirSyncNoService| To this day, I still do not know exactly what that means.|
|DirSyncSfBUserNeedsProvisioning| This appears to be a temporal state before DirSyncSfBUser|
|DirSyncSfBUser| Enabled in SfB Online, has a SipAddress and has a RegistrarPool, this is the best value we can get.|
|EnabledUserWithNoService|Active users without any license|
|EnabledUserWithTeamsLicense|Active users with Teams license|
|HybridOnlineDisabledUserNeedsProvisioning| User account disabled in SfB online, hasn't a SipAddress attribute online and OnPremHostingProvider is not empty.|
|HybridOnlineDisabledUserWithDeletedLicenses| It's like HybridOnlineDisabledUser but, it seems that license is not assigned.|
|HybridOnlineDisabledUser| User account disabled in SfB online, has a SipAddress attribute online and OnPremHostingProvider is not empty.|
|HybridOnlineSfBUserWithDeletedLicenses| Same as HybridOnlineSfBUser but judging by the name, it seems that license is not present.|
|HybridOnlineSfBUserWithTeamsLicense||
|HybridOnlineTeamsOnlyUserNeedsProvisioningToAD||
|HybridOnlineSfBUser| User account enabled and DirSynched, has a SipAddress and a OnPremHostingProvider and RegistrarPool.|
|HybridOnpremActiveDirectoryDisabledUser||
|HybridOnpremActiveDirectoryDisabledUserWithMCOValidationError||
|HybridOnpremDisabledUser| User account disabled in SfB OnPrem, OnPremHostingProvider has "SRV:" value and RegistrarPool is empty.|
|HybridOnpremSfBUserWithMCOValidationError||
|HybridOnpremSfBUserWithTeamsLicense||
|HybridOnpremSfBUserWithTeamsLicenseWithMCOValidationError||
|HybridOnpremSfBUser| According to Johan Delimon's Blog, the account is created at Customer AD, DirSynched and uses SfB OnPrem, we can judge this by the presence of OnPremHostingProvider.|
|HybridOnpremTeamsOnlyUser||
|HybridOnpremUserNotLicensedForService||
|PureOnlineActiveDirectoryDisabledUserPendingAttributeRemovalFromAD||
|PureOnlineActiveDirectoryDisabledUser||
|PureOnlineApplicationInstance||
|PureOnlineEnabledUserWithNoService||
|PureOnlineEnabledUserWithSfBAndTeamsLicense||
|PureOnlineEnabledUserWithTeamsLicense||
|PureOnlineNoServiceWithDeletedLicenses| User account created in Office 365, has no local AD account, so is not DirSynched, has no SfB license.|
|PureOnlineNoService| I still do not know exactly what that means.|
|PureOnlineSfBUserWithTeamsLicense||
|PureOnlineSfBUser| User account created in Office 365, has no local AD account, so is not DirSynched, and uses SfB Online.|
|PureOnlineTeamsOnlyUserFailedProvisioningToBVD|Enterprise Voice is enabled, and a number is added to the user. The number needs to synchronise into Microsoft's Business Voice Directory (BVD). When calls are received to Microsoft SBC's, the BVD is checked to determine which user the call should be routed to.|
|PureOnlineTeamsOnlyUserNeedsProvisioningToAD||
|PureOnlineTeamsOnlyUser||
|PureOnlineTeamsUser||
|PureOnlineUserNotLicensedForServiceFailedPublishingToAAD||
|PureOnlineUserNotLicensedForServicePendingAttributeRemovalFromAD||
|PureOnlineUserNotLicensedForService||

#### The InterpretedUserType value is composed of four other possible values, following you will find these collected values and its possible meaning:

# UserType table

| UserType | Possible Description |
|------- | -------------------- |
|NoService|User does not meet any of the other UserTypes criteria; These are generally unlicensed users |
|SfBUser|User has an enabled SfB Online base license|
|TeamsUser|User has an Enabled Teams Online license and no Enabled SfB Online base license (Note: Don't be confused about this; we still require SfB Online License) |
|FreemiumUser|User is assigned a Teams Online Freemium license or an SfB Online Freemium license |
|DisabledUser|User is not an Application Endpoint, and the AD object is Disabled in UserAccountControl regardless of Online license state |
|AppEndpoint|User is an Application Endpoint |

# UserSubType table

| UserSubType | Possible Description |
|------- | -------------------- |
|PureOnline | User is not configured for AAD Connect |
|HybridOnPrem | User is enabled for AAD Connect, the user is syncing on-prem SfB AD attributes and the user’s on-prem msRTCSIP-DeploymentLocator attribute is “SRV:”; does not indicate or take into consideration the status of ShareSipAddressSpace |
|HybridOnline | User is enabled for AAD Connect, the user is syncing on-prem SfB AD attributes and the user’s on-prem msRTCSIP-DeploymentLocator attribute is an Online hosting provider, usually “http://sipfed.online.lync.com” ; does not indicate or take into consideration the status of ShareSipAddressSpace |
|DirSyncDisabled | User is explicitly disabled for AAD Connect; considered the same as PureOnline |
|DirSync| User is enabled for AAD Connect but the user is not syncing on-prem SfB AD attributes, specifically the msRTCSIP-DeploymentLocator attribute |

# UserState table

| UserState | Possible Description |
|------- | -------------------- |
| WithMCOValidationError | User failed provisioning with a tenant admin correctable error. The user’s MCOValidationError property will contain details of the error and how to correct it. |
|FailedProvisioning | User failed provisioning and will be retried in the next retry interval. |
|FailedBvdProvisioning |User failed provisioning and will be retried in the next retry interval. |
|NeedsProvisioning| User is waiting for provisioning to start. |
|WithDeletedLicenses| User’s LicenseRemovalTimeStamp is set. |
|PendingXForestMove | User has a XForestMovePolicy set. |

# UserUserMncState table
| UserMncState | Possible Description |
|------- | -------------------- |
|NotInPDL | User has a Preferred Data Location set but is not assigned an SfB Online registrar pool in the current AD Forest. Caveat: User could be in their PDL but not provisioned yet. |
|InPDL | User has a Preferred Data Location set and is assigned an SfB Online registrar pool in the current AD Forest|
