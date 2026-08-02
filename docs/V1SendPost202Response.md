

# V1SendPost202Response


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **UUID** | Lockally identifier; use with GET /v1/messages/{id}. |  |
|**messageId** | **String** | RFC 5322 Message-ID (with angle brackets). |  |
|**status** | [**StatusEnum**](#StatusEnum) | \&quot;scheduled\&quot; when send_at is in the future. |  |
|**warning** | **String** |  |  [optional] |



## Enum: StatusEnum

| Name | Value |
|---- | -----|
| QUEUED | &quot;queued&quot; |
| SCHEDULED | &quot;scheduled&quot; |



