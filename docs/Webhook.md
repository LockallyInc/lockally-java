

# Webhook


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **UUID** |  |  |
|**tenantId** | **UUID** |  |  |
|**url** | **URI** |  |  |
|**events** | **List&lt;String&gt;** |  |  |
|**paused** | **Boolean** |  |  |
|**pausedAt** | **OffsetDateTime** |  |  [optional] |
|**lastSuccessAt** | **OffsetDateTime** |  |  [optional] |
|**lastFailureAt** | **OffsetDateTime** |  |  [optional] |
|**consecutiveFailures** | **Integer** |  |  |
|**createdAt** | **OffsetDateTime** |  |  |
|**signingSecret** | **String** | Hex-encoded HMAC-SHA256 key. Present ONLY on POST response. |  [optional] |



