

# MigrationDNSCheck

Live DNS readiness of the destination domains, for deciding when to cut over. `ready` is true only when every domain's MX points at Lockally and its SPF authorises it.

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**ready** | **Boolean** |  |  |
|**domains** | [**List&lt;MigrationDomainDNS&gt;**](MigrationDomainDNS.md) |  |  |



