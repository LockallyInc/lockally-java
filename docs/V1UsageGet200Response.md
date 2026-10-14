

# V1UsageGet200Response


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**mailboxesActive** | **Integer** | Mailboxes that are neither disabled nor soft-deleted. |  |
|**mailboxesTotal** | **Integer** | All mailboxes for this tenant, including disabled/soft-deleted. |  [optional] |
|**domainsVerified** | **Integer** | Domains that have passed DNS verification. |  [optional] |
|**domainsTotal** | **Integer** |  |  [optional] |
|**messagesSentLast60s** | **Integer** | Sends in the 60-second window ending now. Used by the rate-cap check. |  [optional] |
|**messagesSentTodayUtc** | **Integer** | Sends since 00:00 UTC. Compared against &#x60;daily_msg_quota&#x60;. |  [optional] |
|**messagesSentLast30d** | **Integer** | Rolling 30-day send count (not calendar month). |  [optional] |
|**bytesStored** | **Long** | Lifetime sum of &#x60;messages.size_bytes&#x60; for this tenant. |  [optional] |
|**rateCapPerMin** | **Integer** | Per-tenant outbound rate cap (sends per minute). |  [optional] |
|**dailyMsgQuota** | **Integer** | Per-tenant daily send quota (UTC day boundary). |  [optional] |
|**webhooksTotal** | **Integer** |  |  [optional] |
|**webhooksPaused** | **Integer** | Webhook subscriptions auto-paused after 50 consecutive failures (LT2). |  [optional] |
|**generatedAt** | **OffsetDateTime** | When this snapshot was generated, RFC 3339 UTC. |  |



