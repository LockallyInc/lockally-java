

# TenantHealthReport

The workspace health snapshot behind the console dashboard. DNS checks are live lookups, so a domain whose DNS cannot be read shows as a warning rather than an error.

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**overallScore** | **Integer** |  |  |
|**checks** | [**List&lt;TenantHealthCheck&gt;**](TenantHealthCheck.md) |  |  |
|**generatedAt** | **OffsetDateTime** |  |  |



