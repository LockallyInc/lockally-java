

# UpdateDirectoryPermissionsRequest


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**contactViewAccess** | [**ContactViewAccessEnum**](#ContactViewAccessEnum) |  |  [optional] |
|**contactEditAccess** | [**ContactEditAccessEnum**](#ContactEditAccessEnum) |  |  [optional] |
|**listManageAccess** | [**ListManageAccessEnum**](#ListManageAccessEnum) |  |  [optional] |
|**externalSharing** | [**ExternalSharingEnum**](#ExternalSharingEnum) |  |  [optional] |



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



