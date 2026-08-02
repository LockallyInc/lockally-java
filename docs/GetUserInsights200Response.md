

# GetUserInsights200Response


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**recentlyAdded** | [**List&lt;UserEvent&gt;**](UserEvent.md) |  |  [optional] |
|**recentlySuspended** | [**List&lt;UserEvent&gt;**](UserEvent.md) |  |  [optional] |
|**inactive30d** | [**List&lt;UserEvent&gt;**](UserEvent.md) |  |  [optional] |
|**seatsUsed** | **Integer** |  |  [optional] |
|**seatsAlloc** | **Integer** |  |  [optional] |
|**seatsCapped** | **Boolean** | True only on tiers with a hard seat cap (Free, Founder). On unlimited/per-seat tiers seats_alloc merely tracks the live mailbox count, so seats_used &#x3D;&#x3D; seats_alloc is normal and must not be read as &#39;at capacity&#39;. |  [optional] |
|**generatedAt** | **OffsetDateTime** |  |  [optional] |



