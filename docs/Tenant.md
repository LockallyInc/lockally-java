

# Tenant


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **UUID** |  |  |
|**slug** | **String** |  |  |
|**displayName** | **String** |  |  |
|**status** | [**StatusEnum**](#StatusEnum) |  |  |
|**plan** | **String** |  |  |
|**rateCapPerMin** | **Integer** | Per-tenant share of the per-VPS 5/min outbound cap (L6). |  |
|**dailyMsgQuota** | **Integer** |  |  |
|**adminEmail** | **String** |  |  |
|**createdAt** | **OffsetDateTime** |  |  |
|**suspendedAt** | **OffsetDateTime** |  |  [optional] |
|**closedAt** | **OffsetDateTime** |  |  [optional] |
|**hardDeleteAfter** | **OffsetDateTime** |  |  [optional] |



## Enum: StatusEnum

| Name | Value |
|---- | -----|
| ACTIVE | &quot;active&quot; |
| SUSPENDED | &quot;suspended&quot; |
| CLOSING | &quot;closing&quot; |
| CLOSED | &quot;closed&quot; |



