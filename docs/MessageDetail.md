

# MessageDetail

A single message with the content captured at send time. Returned only by GET /v1/messages/{id} (the list stays summary-only). Attachments are not returned. 

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **UUID** |  |  |
|**tenantId** | **UUID** |  |  |
|**messageId** | **String** | RFC 5322 Message-ID header, including angle brackets. |  |
|**sender** | **String** |  |  |
|**recipients** | **List&lt;String&gt;** |  |  |
|**subject** | **String** |  |  [optional] |
|**status** | [**StatusEnum**](#StatusEnum) |  |  |
|**queuedAt** | **OffsetDateTime** |  |  |
|**updatedAt** | **OffsetDateTime** |  |  |
|**bounceReason** | **String** |  |  [optional] |
|**sizeBytes** | **Integer** |  |  [optional] |
|**metadata** | **Map&lt;String, String&gt;** | The sender&#39;s own key/value from the send request. Always present; &#x60;{}&#x60; when none was set. |  [optional] |
|**tags** | **List&lt;String&gt;** | Grouping labels, lowercased and deduplicated. Always present; &#x60;[]&#x60; when none were set. |  [optional] |
|**from** | **String** |  |  [optional] |
|**to** | **List&lt;String&gt;** |  |  [optional] |
|**cc** | **List&lt;String&gt;** |  |  [optional] |
|**bcc** | **List&lt;String&gt;** |  |  [optional] |
|**text** | **String** |  |  [optional] |
|**html** | **String** |  |  [optional] |
|**headers** | **Map&lt;String, String&gt;** |  |  [optional] |



## Enum: StatusEnum

| Name | Value |
|---- | -----|
| QUEUED | &quot;queued&quot; |
| SENDING | &quot;sending&quot; |
| DELIVERED | &quot;delivered&quot; |
| BOUNCED | &quot;bounced&quot; |
| DEFERRED | &quot;deferred&quot; |
| COMPLAINT | &quot;complaint&quot; |



