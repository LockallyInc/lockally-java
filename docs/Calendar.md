

# Calendar


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **UUID** |  |  |
|**tenantId** | **UUID** |  |  |
|**name** | **String** |  |  |
|**color** | **String** |  |  [optional] |
|**ownerEmail** | **String** |  |  [optional] |
|**description** | **String** |  |  [optional] |
|**visibility** | [**VisibilityEnum**](#VisibilityEnum) |  |  |
|**feedUrl** | **URI** |  |  [optional] |
|**eventCount** | **Integer** |  |  [optional] |
|**createdAt** | **OffsetDateTime** |  |  |
|**updatedAt** | **OffsetDateTime** |  |  |



## Enum: VisibilityEnum

| Name | Value |
|---- | -----|
| PRIVATE | &quot;private&quot; |
| TENANT | &quot;tenant&quot; |



