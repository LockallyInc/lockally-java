

# BillingStatus


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**plan** | **String** |  |  |
|**displayName** | **String** |  |  |
|**mode** | [**ModeEnum**](#ModeEnum) |  |  |
|**rateCapPerMin** | **Integer** |  |  |
|**monthlyIncludedSends** | **Integer** |  |  |
|**msgsThisPeriod** | **Integer** |  |  |
|**status** | [**StatusEnum**](#StatusEnum) |  |  |
|**priceNairaPerSeat** | **Integer** |  |  |
|**subscribedAt** | **OffsetDateTime** |  |  [optional] |
|**currentPeriodEnd** | **OffsetDateTime** |  |  [optional] |
|**createdAt** | **OffsetDateTime** |  |  |
|**sendUnitsBalance** | **Integer** |  |  |
|**sendUnitsNextExpiry** | **OffsetDateTime** |  |  [optional] |
|**unitBundles** | [**List&lt;UnitBundle&gt;**](UnitBundle.md) |  |  |
|**catalog** | [**List&lt;PlanCatalogEntry&gt;**](PlanCatalogEntry.md) |  |  |



## Enum: ModeEnum

| Name | Value |
|---- | -----|
| API | &quot;api&quot; |
| BUSINESS | &quot;business&quot; |
| BOTH | &quot;both&quot; |



## Enum: StatusEnum

| Name | Value |
|---- | -----|
| ACTIVE | &quot;active&quot; |
| SUSPENDED | &quot;suspended&quot; |



