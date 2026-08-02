

# BatchResult


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**index** | **Integer** |  |  [optional] |
|**id** | **UUID** |  |  [optional] |
|**messageId** | **String** |  |  [optional] |
|**status** | [**StatusEnum**](#StatusEnum) |  |  [optional] |
|**error** | **String** | Present when this message failed; the others are then absent. |  [optional] |



## Enum: StatusEnum

| Name | Value |
|---- | -----|
| QUEUED | &quot;queued&quot; |
| SCHEDULED | &quot;scheduled&quot; |
| SUPPRESSED | &quot;suppressed&quot; |



