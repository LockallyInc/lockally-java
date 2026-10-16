

# Message


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



## Enum: StatusEnum

| Name | Value |
|---- | -----|
| QUEUED | &quot;queued&quot; |
| SENDING | &quot;sending&quot; |
| DELIVERED | &quot;delivered&quot; |
| BOUNCED | &quot;bounced&quot; |
| DEFERRED | &quot;deferred&quot; |
| COMPLAINT | &quot;complaint&quot; |



