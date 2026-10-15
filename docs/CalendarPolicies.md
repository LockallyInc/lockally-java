

# CalendarPolicies


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**tenantId** | **UUID** |  |  |
|**maxMeetingDurationMins** | **Integer** |  |  [optional] |
|**workingHoursStart** | **String** |  |  [optional] |
|**workingHoursEnd** | **String** |  |  [optional] |
|**bookingWindowDays** | **Integer** |  |  [optional] |
|**recurringMeetingLimit** | **Integer** |  |  [optional] |
|**resourceApprovalMode** | [**ResourceApprovalModeEnum**](#ResourceApprovalModeEnum) |  |  [optional] |
|**externalInvitesAllowed** | **Boolean** |  |  [optional] |
|**externalSharingAllowed** | **Boolean** |  |  [optional] |
|**publicLinksEnabled** | **Boolean** |  |  [optional] |
|**createdAt** | **OffsetDateTime** |  |  [optional] |
|**updatedAt** | **OffsetDateTime** |  |  [optional] |



## Enum: ResourceApprovalModeEnum

| Name | Value |
|---- | -----|
| AUTO_APPROVE | &quot;auto_approve&quot; |
| REQUIRE_APPROVAL | &quot;require_approval&quot; |
| RESTRICTED | &quot;restricted&quot; |



