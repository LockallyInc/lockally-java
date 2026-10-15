

# CalendarIntegration


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **UUID** |  |  |
|**tenantId** | **UUID** |  |  |
|**provider** | [**ProviderEnum**](#ProviderEnum) |  |  |
|**label** | **String** |  |  [optional] |
|**status** | [**StatusEnum**](#StatusEnum) |  |  |
|**lastSyncAt** | **OffsetDateTime** |  |  [optional] |
|**errorMessage** | **String** |  |  [optional] |
|**createdAt** | **OffsetDateTime** |  |  |
|**updatedAt** | **OffsetDateTime** |  |  |



## Enum: ProviderEnum

| Name | Value |
|---- | -----|
| EXCHANGE | &quot;exchange&quot; |
| GOOGLE_CALENDAR | &quot;google_calendar&quot; |
| TEAMS | &quot;teams&quot; |
| ZOOM | &quot;zoom&quot; |
| ERP | &quot;erp&quot; |



## Enum: StatusEnum

| Name | Value |
|---- | -----|
| CONNECTED | &quot;connected&quot; |
| DISCONNECTED | &quot;disconnected&quot; |
| ERROR | &quot;error&quot; |
| SYNCING | &quot;syncing&quot; |



