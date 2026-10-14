

# V1ApiKeysPost201Response


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **UUID** |  |  |
|**tenantId** | **UUID** |  |  |
|**prefix** | **String** | 8-char public prefix; safe to store and display. |  |
|**scopes** | **List&lt;String&gt;** |  |  |
|**label** | **String** |  |  |
|**lastUsedAt** | **OffsetDateTime** |  |  [optional] |
|**revokedAt** | **OffsetDateTime** |  |  [optional] |
|**createdAt** | **OffsetDateTime** |  |  |
|**secret** | **String** | The full &#x60;lk_live_&lt;prefix&gt;_&lt;secret&gt;&#x60; token. Shown ONCE. |  |



