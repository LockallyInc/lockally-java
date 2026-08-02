

# Admin


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



## Enum: RoleEnum

| Name | Value |
|---- | -----|
| ADMIN | &quot;admin&quot; |
| VIEWER | &quot;viewer&quot; |



