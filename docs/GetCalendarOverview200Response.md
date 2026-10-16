

# GetCalendarOverview200Response


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**totalCalendars** | **Integer** |  |  [optional] |
|**activeCalendars** | **Integer** | Calendars with an event created, edited or held in the last 30 days. |  [optional] |
|**sharedCalendars** | **Integer** | Calendars visible to the whole organization. |  [optional] |
|**eventsThisMonth** | **Integer** | Events on every calendar, in the account&#39;s own timezone. |  [optional] |
|**upcomingOrgEvents** | **Integer** | Future events on organization-visible calendars. |  [optional] |
|**bookableResources** | **Integer** | Resources that are not disabled. |  [optional] |
|**accessGranted** | **Integer** | People who own a calendar or are named on one. |  [optional] |
|**accessOrgWide** | **Integer** | Everyone who can see an organization calendar; 0 when none exists. |  [optional] |
|**activity** | [**List&lt;GetCalendarOverview200ResponseActivityInner&gt;**](GetCalendarOverview200ResponseActivityInner.md) |  |  [optional] |



