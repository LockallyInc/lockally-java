

# DNSRecord


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**type** | [**TypeEnum**](#TypeEnum) |  |  |
|**name** | **String** |  |  |
|**value** | **String** |  |  |
|**ttl** | **Integer** |  |  |
|**priority** | **Integer** | MX records only. |  [optional] |
|**purpose** | [**PurposeEnum**](#PurposeEnum) |  |  |



## Enum: TypeEnum

| Name | Value |
|---- | -----|
| TXT | &quot;TXT&quot; |
| MX | &quot;MX&quot; |



## Enum: PurposeEnum

| Name | Value |
|---- | -----|
| VERIFICATION | &quot;verification&quot; |
| SPF | &quot;spf&quot; |
| DKIM | &quot;dkim&quot; |
| MX_PRIMARY | &quot;mx-primary&quot; |
| MX_BACKUP | &quot;mx-backup&quot; |
| DMARC | &quot;dmarc&quot; |



