

# APIKey


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
|**test** | **Boolean** | True for an lk_test_* key: the whole request path runs but a send never reaches the mail server and nothing counts against the account. |  [optional] |
|**expiresAt** | **OffsetDateTime** | When the key stops authenticating. Null means it does not expire, which is how every key behaved before expiry existed. Enforced at authentication, so the key fails the first request after this moment rather than whenever a sweep runs.  |  [optional] |
|**rotatedTo** | **UUID** | The successor issued by &#x60;POST /v1/api-keys/{id}/rotate&#x60;. Set on the PREDECESSOR, so you can see which key replaced this one while both still work through the overlap window.  |  [optional] |



