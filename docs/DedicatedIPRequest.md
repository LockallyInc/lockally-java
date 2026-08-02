

# DedicatedIPRequest


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **UUID** |  |  |
|**tenantId** | **UUID** |  |  |
|**status** | [**StatusEnum**](#StatusEnum) |  |  |
|**note** | **String** |  |  [optional] |
|**adminNote** | **String** |  |  [optional] |
|**createdAt** | **OffsetDateTime** |  |  |
|**resolvedAt** | **OffsetDateTime** |  |  [optional] |



## Enum: StatusEnum

| Name | Value |
|---- | -----|
| PENDING | &quot;pending&quot; |
| APPROVED | &quot;approved&quot; |
| REJECTED | &quot;rejected&quot; |



