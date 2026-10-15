

# ThreadMessageBody


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **UUID** |  |  |
|**direction** | [**DirectionEnum**](#DirectionEnum) |  |  |
|**rfcMessageId** | **String** | The Internet Message-ID |  |
|**inReplyTo** | **String** |  |  [optional] |
|**subject** | **String** |  |  [optional] |
|**from** | **String** |  |  |
|**to** | **List&lt;String&gt;** |  |  |
|**snippet** | **String** |  |  [optional] |
|**hasAttachments** | **Boolean** |  |  |
|**attachments** | [**List&lt;Attachment&gt;**](Attachment.md) |  |  [optional] |
|**annotations** | [**Annotations**](Annotations.md) |  |  [optional] |
|**receivedAt** | **OffsetDateTime** |  |  |
|**body** | [**ThreadMessageBodyAllOfBody**](ThreadMessageBodyAllOfBody.md) |  |  [optional] |



## Enum: DirectionEnum

| Name | Value |
|---- | -----|
| INBOUND | &quot;inbound&quot; |
| OUTBOUND | &quot;outbound&quot; |



