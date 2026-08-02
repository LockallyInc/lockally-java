

# V1ApiKeysPostRequest


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**label** | **String** | Free-text identifier shown in the dashboard. |  |
|**scopes** | [**List&lt;ScopesEnum&gt;**](#List&lt;ScopesEnum&gt;) | Allowed scopes on this key. |  |



## Enum: List&lt;ScopesEnum&gt;

| Name | Value |
|---- | -----|
| TENANT_READ | &quot;tenant:read&quot; |
| TENANT_ADMIN | &quot;tenant:admin&quot; |
| MAILBOXES_READ | &quot;mailboxes:read&quot; |
| MAILBOXES_WRITE | &quot;mailboxes:write&quot; |
| SEND_READ | &quot;send:read&quot; |
| SEND_WRITE | &quot;send:write&quot; |
| WEBHOOKS_READ | &quot;webhooks:read&quot; |
| WEBHOOKS_WRITE | &quot;webhooks:write&quot; |
| DOMAINS_READ | &quot;domains:read&quot; |
| DOMAINS_WRITE | &quot;domains:write&quot; |



