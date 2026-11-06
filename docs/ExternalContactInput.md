

# ExternalContactInput


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**email** | **String** |  |  |
|**name** | **String** | Defaults to the email address when empty. |  [optional] |
|**phone** | **String** |  |  [optional] |
|**company** | **String** |  |  [optional] |
|**notes** | **String** |  |  [optional] |
|**contactType** | [**ContactTypeEnum**](#ContactTypeEnum) |  |  [optional] |
|**department** | **String** |  |  [optional] |
|**role** | **String** |  |  [optional] |
|**status** | [**StatusEnum**](#StatusEnum) |  |  [optional] |



## Enum: ContactTypeEnum

| Name | Value |
|---- | -----|
| INTERNAL | &quot;internal&quot; |
| EXTERNAL | &quot;external&quot; |



## Enum: StatusEnum

| Name | Value |
|---- | -----|
| ACTIVE | &quot;active&quot; |
| DISABLED | &quot;disabled&quot; |



