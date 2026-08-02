

# UpdateCalendarPoliciesRequest


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**maxMeetingDurationMins** | **Integer** |  |  [optional] |
|**workingHoursStart** | **String** |  |  [optional] |
|**workingHoursEnd** | **String** |  |  [optional] |
|**bookingWindowDays** | **Integer** |  |  [optional] |
|**recurringMeetingLimit** | **Integer** |  |  [optional] |
|**resourceApprovalMode** | [**ResourceApprovalModeEnum**](#ResourceApprovalModeEnum) |  |  [optional] |
|**externalInvitesAllowed** | **Boolean** |  |  [optional] |
|**externalSharingAllowed** | **Boolean** |  |  [optional] |
|**publicLinksEnabled** | **Boolean** |  |  [optional] |



## Enum: ResourceApprovalModeEnum

| Name | Value |
|---- | -----|
| AUTO_APPROVE | &quot;auto_approve&quot; |
| REQUIRE_APPROVAL | &quot;require_approval&quot; |
| RESTRICTED | &quot;restricted&quot; |



