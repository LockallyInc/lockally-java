

# ReturnPath


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**status** | [**StatusEnum**](#StatusEnum) |  |  |
|**host** | **String** |  |  |
|**records** | [**List&lt;DNSRecord&gt;**](DNSRecord.md) |  |  |
|**check** | [**ReturnPathCheck**](ReturnPathCheck.md) |  |  [optional] |
|**requestedAt** | **OffsetDateTime** |  |  [optional] |
|**verifiedAt** | **OffsetDateTime** |  |  [optional] |



## Enum: StatusEnum

| Name | Value |
|---- | -----|
| FALSE | &quot;false&quot; |
| PENDING | &quot;pending&quot; |
| ACTIVE | &quot;active&quot; |



