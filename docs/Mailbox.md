

# Mailbox


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **UUID** |  |  |
|**tenantId** | **UUID** |  |  |
|**domainId** | **UUID** |  |  |
|**email** | **String** |  |  |
|**quotaBytes** | **Long** |  |  |
|**disabled** | **Boolean** |  |  |
|**disabledAt** | **OffsetDateTime** |  |  [optional] |
|**softDeletedAt** | **OffsetDateTime** |  |  [optional] |
|**hardDeleteAfter** | **OffsetDateTime** |  |  [optional] |
|**createdAt** | **OffsetDateTime** |  |  |
|**password** | **String** | ONLY present on POST response when lockally generated the password. Shown once. |  [optional] |



