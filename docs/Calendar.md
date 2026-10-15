

# Calendar


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **UUID** |  |  |
|**tenantId** | **UUID** |  |  |
|**name** | **String** |  |  |
|**color** | **String** |  |  [optional] |
|**ownerEmail** | **String** |  |  [optional] |
|**description** | **String** |  |  [optional] |
|**calendarType** | [**CalendarTypeEnum**](#CalendarTypeEnum) | What the calendar is for. Separate from visibility, which is who may see it: a team calendar can be open to everyone and a department one restricted to named people. \&quot;personal\&quot; is a person&#39;s own and is not listed in the console&#39;s management table.  |  [optional] |
|**ownerUnit** | **String** | The owning department or office. Empty on a personal calendar, which is owned by owner_email. |  [optional] |
|**visibility** | [**VisibilityEnum**](#VisibilityEnum) |  |  |
|**accessDepartment** | **String** | Which department may see it, when visibility is \&quot;department\&quot;. Matched against the department recorded on a user, so access follows a person between departments with no membership list to maintain.  |  [optional] |
|**status** | [**StatusEnum**](#StatusEnum) | Archived keeps the calendar, its events and its feed, and stops it taking new events. |  [optional] |
|**feedUrl** | **URI** |  |  [optional] |
|**eventCount** | **Integer** |  |  [optional] |
|**createdAt** | **OffsetDateTime** |  |  |
|**updatedAt** | **OffsetDateTime** |  |  |



## Enum: CalendarTypeEnum

| Name | Value |
|---- | -----|
| PERSONAL | &quot;personal&quot; |
| ORGANIZATION | &quot;organization&quot; |
| DEPARTMENT | &quot;department&quot; |
| TEAM | &quot;team&quot; |
| SHARED | &quot;shared&quot; |



## Enum: VisibilityEnum

| Name | Value |
|---- | -----|
| PRIVATE | &quot;private&quot; |
| TENANT | &quot;tenant&quot; |
| DEPARTMENT | &quot;department&quot; |



## Enum: StatusEnum

| Name | Value |
|---- | -----|
| ACTIVE | &quot;active&quot; |
| ARCHIVED | &quot;archived&quot; |



