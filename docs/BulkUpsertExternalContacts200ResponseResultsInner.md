

# BulkUpsertExternalContacts200ResponseResultsInner


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**index** | **Integer** |  |  |
|**externalId** | **String** |  |  |
|**status** | [**StatusEnum**](#StatusEnum) |  |  |
|**contact** | [**Contact**](Contact.md) |  |  [optional] |
|**error** | **String** |  |  [optional] |



## Enum: StatusEnum

| Name | Value |
|---- | -----|
| CREATED | &quot;created&quot; |
| UPDATED | &quot;updated&quot; |
| ERROR | &quot;error&quot; |



