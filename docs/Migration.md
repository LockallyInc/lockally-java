

# Migration


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **UUID** |  |  |
|**tenantId** | **UUID** |  |  |
|**credentialId** | **UUID** |  |  |
|**name** | **String** |  |  |
|**status** | [**StatusEnum**](#StatusEnum) |  |  |
|**sourceProvider** | **String** |  |  |
|**sourceSummary** | **String** |  |  [optional] |
|**settings** | [**MigrationSettings**](MigrationSettings.md) |  |  [optional] |
|**errorMessage** | **String** |  |  [optional] |
|**startedAt** | **OffsetDateTime** |  |  [optional] |
|**completedAt** | **OffsetDateTime** |  |  [optional] |
|**mailboxCount** | **Integer** |  |  |
|**createdAt** | **OffsetDateTime** |  |  |
|**updatedAt** | **OffsetDateTime** |  |  |



## Enum: StatusEnum

| Name | Value |
|---- | -----|
| DRAFT | &quot;draft&quot; |
| DISCOVERING | &quot;discovering&quot; |
| DISCOVERED | &quot;discovered&quot; |
| MAPPED | &quot;mapped&quot; |
| PILOT_RUNNING | &quot;pilot_running&quot; |
| PILOT_COMPLETE | &quot;pilot_complete&quot; |
| RUNNING | &quot;running&quot; |
| STAGED | &quot;staged&quot; |
| CUTOVER_PENDING | &quot;cutover_pending&quot; |
| FINAL_SYNCING | &quot;final_syncing&quot; |
| VALIDATING | &quot;validating&quot; |
| COMPLETED | &quot;completed&quot; |
| FAILED | &quot;failed&quot; |
| CANCELLED | &quot;cancelled&quot; |



