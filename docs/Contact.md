

# Contact


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **UUID** |  |  |
|**tenantId** | **UUID** |  |  |
|**name** | **String** |  |  |
|**email** | **String** |  |  |
|**phone** | **String** |  |  [optional] |
|**company** | **String** |  |  [optional] |
|**notes** | **String** |  |  [optional] |
|**contactType** | [**ContactTypeEnum**](#ContactTypeEnum) |  |  |
|**source** | **String** |  |  [optional] |
|**department** | **String** |  |  [optional] |
|**role** | **String** |  |  [optional] |
|**status** | **String** |  |  |
|**createdAt** | **OffsetDateTime** |  |  |
|**updatedAt** | **OffsetDateTime** |  |  |
|**externalSystem** | **String** | The system that owns this contact&#39;s external id. Absent on contacts made by hand. |  [optional] |
|**externalId** | **String** | The contact&#39;s id in &#x60;external_system&#x60;. Absent on contacts made by hand. |  [optional] |



## Enum: ContactTypeEnum

| Name | Value |
|---- | -----|
| INTERNAL | &quot;internal&quot; |
| EXTERNAL | &quot;external&quot; |



