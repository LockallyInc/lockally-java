

# SendEmail200Response


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **UUID** | Present on a test-mode send; absent when suppressed. |  [optional] |
|**messageId** | **String** | RFC 5322 Message-ID. On a test send the domain is test.lockally.com. Absent when suppressed. |  [optional] |
|**status** | [**StatusEnum**](#StatusEnum) |  |  |
|**warning** | **String** | On a suppressed send, explains that nothing was sent. |  [optional] |



## Enum: StatusEnum

| Name | Value |
|---- | -----|
| SUPPRESSED | &quot;suppressed&quot; |
| DELIVERED | &quot;delivered&quot; |



