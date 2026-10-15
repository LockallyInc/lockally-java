

# MigrationCredential


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **UUID** |  |  |
|**tenantId** | **UUID** |  |  |
|**provider** | [**ProviderEnum**](#ProviderEnum) |  |  |
|**encryptionKeyId** | **String** |  |  [optional] |
|**label** | **String** |  |  [optional] |
|**createdAt** | **OffsetDateTime** |  |  |
|**updatedAt** | **OffsetDateTime** |  |  |



## Enum: ProviderEnum

| Name | Value |
|---- | -----|
| IMAP | &quot;imap&quot; |
| GOOGLE | &quot;google&quot; |
| MICROSOFT | &quot;microsoft&quot; |
| GENERIC | &quot;generic&quot; |



