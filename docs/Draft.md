

# Draft


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **UUID** |  |  |
|**mailboxId** | **UUID** |  |  |
|**mailbox** | **String** |  |  [optional] |
|**threadId** | **UUID** |  |  [optional] |
|**to** | **List&lt;String&gt;** |  |  |
|**cc** | **List&lt;String&gt;** |  |  [optional] |
|**subject** | **String** |  |  [optional] |
|**bodyText** | **String** |  |  [optional] |
|**status** | [**StatusEnum**](#StatusEnum) |  |  |
|**policyFlags** | **Map&lt;String, Object&gt;** |  |  |
|**reviewedAt** | **OffsetDateTime** |  |  [optional] |
|**sentMessageId** | **UUID** |  |  [optional] |
|**createdAt** | **OffsetDateTime** |  |  |
|**updatedAt** | **OffsetDateTime** |  |  |



## Enum: StatusEnum

| Name | Value |
|---- | -----|
| PENDING_APPROVAL | &quot;pending_approval&quot; |
| SENT | &quot;sent&quot; |
| REJECTED | &quot;rejected&quot; |
| CANCELLED | &quot;cancelled&quot; |



