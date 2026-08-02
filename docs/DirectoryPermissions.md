

# DirectoryPermissions


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**tenantId** | **UUID** |  |  |
|**contactViewAccess** | [**ContactViewAccessEnum**](#ContactViewAccessEnum) |  |  |
|**contactEditAccess** | [**ContactEditAccessEnum**](#ContactEditAccessEnum) |  |  |
|**listManageAccess** | [**ListManageAccessEnum**](#ListManageAccessEnum) |  |  |
|**externalSharing** | [**ExternalSharingEnum**](#ExternalSharingEnum) |  |  |
|**createdAt** | **OffsetDateTime** |  |  [optional] |
|**updatedAt** | **OffsetDateTime** |  |  [optional] |



## Enum: ContactViewAccessEnum

| Name | Value |
|---- | -----|
| ALL_USERS | &quot;all_users&quot; |
| SAME_DEPARTMENT | &quot;same_department&quot; |
| ADMINS_ONLY | &quot;admins_only&quot; |



## Enum: ContactEditAccessEnum

| Name | Value |
|---- | -----|
| ALL_USERS | &quot;all_users&quot; |
| ADMINS_ONLY | &quot;admins_only&quot; |



## Enum: ListManageAccessEnum

| Name | Value |
|---- | -----|
| ALL_USERS | &quot;all_users&quot; |
| LIST_OWNERS | &quot;list_owners&quot; |
| ADMINS_ONLY | &quot;admins_only&quot; |



## Enum: ExternalSharingEnum

| Name | Value |
|---- | -----|
| ALLOWED | &quot;allowed&quot; |
| RESTRICTED | &quot;restricted&quot; |
| DISABLED | &quot;disabled&quot; |



