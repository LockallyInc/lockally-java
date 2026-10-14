

# AdminFull


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **UUID** |  |  |
|**tenantId** | **UUID** |  |  |
|**email** | **String** |  |  |
|**displayName** | **String** |  |  [optional] |
|**role** | [**RoleEnum**](#RoleEnum) |  |  |
|**lastLoginAt** | **OffsetDateTime** |  |  [optional] |
|**createdAt** | **OffsetDateTime** |  |  |
|**disabled** | **Boolean** |  |  |
|**disabledAt** | **OffsetDateTime** |  |  [optional] |
|**password** | **String** | Present ONLY on POST response when lockally generated the password. Shown once. |  [optional] |



## Enum: RoleEnum

| Name | Value |
|---- | -----|
| ADMIN | &quot;admin&quot; |
| VIEWER | &quot;viewer&quot; |



