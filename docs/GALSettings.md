

# GALSettings


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**tenantId** | **UUID** |  |  |
|**galEnabled** | **Boolean** |  |  |
|**hideFromDirectory** | **Boolean** |  |  |
|**departmentGrouping** | **Boolean** |  |  |
|**searchVisibility** | [**SearchVisibilityEnum**](#SearchVisibilityEnum) |  |  |
|**includeExternalContacts** | **Boolean** |  |  |
|**lastIndexRebuiltAt** | **OffsetDateTime** |  |  [optional] |
|**lastSyncedAt** | **OffsetDateTime** |  |  [optional] |
|**createdAt** | **OffsetDateTime** |  |  [optional] |
|**updatedAt** | **OffsetDateTime** |  |  [optional] |



## Enum: SearchVisibilityEnum

| Name | Value |
|---- | -----|
| ALL_USERS | &quot;all_users&quot; |
| SAME_DEPARTMENT | &quot;same_department&quot; |
| ADMINS_ONLY | &quot;admins_only&quot; |



