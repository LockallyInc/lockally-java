

# V1ApiKeysPostRequest


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**label** | **String** | Free-text identifier shown in the dashboard. |  |
|**scopes** | [**List&lt;ScopesEnum&gt;**](#List&lt;ScopesEnum&gt;) | Allowed scopes on this key. |  |
|**test** | **Boolean** | Issue a test key (&#x60;lk_test_&#x60; prefix). A test key accepts sends, records them and fires a simulated delivery webhook without sending mail, and counts against no limit or allowance.  |  [optional] |



## Enum: List&lt;ScopesEnum&gt;

| Name | Value |
|---- | -----|
| TENANT_READ | &quot;tenant:read&quot; |
| TENANT_ADMIN | &quot;tenant:admin&quot; |
| MAILBOXES_READ | &quot;mailboxes:read&quot; |
| MAILBOXES_WRITE | &quot;mailboxes:write&quot; |
| DIRECTORY_SYNC | &quot;directory:sync&quot; |
| INBOXES_READ | &quot;inboxes:read&quot; |
| INBOXES_WRITE | &quot;inboxes:write&quot; |
| SEND_READ | &quot;send:read&quot; |
| SEND_WRITE | &quot;send:write&quot; |
| TEMPLATES_READ | &quot;templates:read&quot; |
| TEMPLATES_WRITE | &quot;templates:write&quot; |
| SUPPRESSIONS_READ | &quot;suppressions:read&quot; |
| SUPPRESSIONS_WRITE | &quot;suppressions:write&quot; |
| WEBHOOKS_READ | &quot;webhooks:read&quot; |
| WEBHOOKS_WRITE | &quot;webhooks:write&quot; |
| DOMAINS_READ | &quot;domains:read&quot; |
| DOMAINS_WRITE | &quot;domains:write&quot; |
| MIGRATIONS_READ | &quot;migrations:read&quot; |
| MIGRATIONS_WRITE | &quot;migrations:write&quot; |



