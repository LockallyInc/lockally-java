

# CalendarMember


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **UUID** |  |  |
|**calendarId** | **UUID** |  |  |
|**tenantId** | **UUID** |  |  |
|**userEmail** | **String** |  |  |
|**role** | [**RoleEnum**](#RoleEnum) |  |  |
|**createdAt** | **OffsetDateTime** |  |  |



## Enum: RoleEnum

| Name | Value |
|---- | -----|
| VIEWER | &quot;viewer&quot; |
| EDITOR | &quot;editor&quot; |
| OWNER | &quot;owner&quot; |



