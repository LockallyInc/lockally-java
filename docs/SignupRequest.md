

# SignupRequest


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**slug** | **String** | Workspace id. 3 to 63 characters of lowercase a-z, 0-9 and hyphens, starting and ending with a letter or digit. Anything else is refused with 400 Invalid workspace id. |  |
|**displayName** | **String** |  |  [optional] |
|**adminEmail** | **String** |  |  |
|**password** | **String** |  |  |
|**mode** | [**ModeEnum**](#ModeEnum) |  |  [optional] |



## Enum: ModeEnum

| Name | Value |
|---- | -----|
| API | &quot;api&quot; |
| BUSINESS | &quot;business&quot; |
| BOTH | &quot;both&quot; |



