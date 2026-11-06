

# BatchResult


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**index** | **Integer** |  |  [optional] |
|**id** | **UUID** |  |  [optional] |
|**messageId** | **String** |  |  [optional] |
|**status** | [**StatusEnum**](#StatusEnum) | \&quot;suppressed\&quot; means every recipient of that slot was on your suppression list, and it carries no id or message_id. \&quot;delivered\&quot; only appears on a test key: the send was simulated, not transmitted. |  [optional] |
|**error** | **String** | Present when this message failed; the others are then absent. |  [optional] |
|**warning** | **String** | Advisory, and NOT a failure. Today the only one is a template variable the template referenced and the request never supplied, which rendered as the empty string. |  [optional] |



## Enum: StatusEnum

| Name | Value |
|---- | -----|
| QUEUED | &quot;queued&quot; |
| SCHEDULED | &quot;scheduled&quot; |
| SUPPRESSED | &quot;suppressed&quot; |
| DELIVERED | &quot;delivered&quot; |



