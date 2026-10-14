

# Domain


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **UUID** |  |  |
|**tenantId** | **UUID** |  |  |
|**domain** | **String** |  |  |
|**verificationToken** | **String** |  |  |
|**verified** | **Boolean** |  |  |
|**verifiedAt** | **OffsetDateTime** |  |  [optional] |
|**dkimSelector** | **String** |  |  |
|**dkimPublicRecord** | **String** |  |  |
|**createdAt** | **OffsetDateTime** |  |  |
|**records** | [**List&lt;DNSRecord&gt;**](DNSRecord.md) | DNS records the tenant must publish under their own DNS. |  [optional] |



