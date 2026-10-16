

# DraftResult


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**draftId** | **UUID** |  |  |
|**status** | [**StatusEnum**](#StatusEnum) |  |  |
|**policyFlags** | [**PolicyFlags**](PolicyFlags.md) |  |  |
|**threadId** | **UUID** |  |  [optional] |
|**sent** | [**AgentSendResult**](AgentSendResult.md) |  |  [optional] |



## Enum: StatusEnum

| Name | Value |
|---- | -----|
| PENDING_APPROVAL | &quot;pending_approval&quot; |
| SENT | &quot;sent&quot; |



