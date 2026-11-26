

# SendMessage


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**from** | **String** | Sender address, alone or as &#x60;Acme Orders &lt;orders@acme.com&gt;&#x60;. |  |
|**fromName** | **String** | Display name shown next to &#x60;from&#x60;. Must match a name given in &#x60;from&#x60;. Cannot contain &#x60;@&#x60; or control characters. |  [optional] |
|**to** | **List&lt;String&gt;** |  |  |
|**cc** | **List&lt;String&gt;** |  |  [optional] |
|**bcc** | **List&lt;String&gt;** |  |  [optional] |
|**subject** | **String** |  |  [optional] |
|**text** | **String** |  |  [optional] |
|**html** | **String** |  |  [optional] |
|**headers** | **Map&lt;String, String&gt;** |  |  [optional] |
|**replyTo** | **String** | Where replies go. Required when &#x60;from&#x60; has no mailbox behind it. The named form &#x60;Acme Support &lt;a@b.com&gt;&#x60; is also accepted. |  [optional] |
|**replyToName** | **String** | Display name shown on &#x60;Reply-To&#x60;. Ignored without &#x60;reply_to&#x60;. |  [optional] |
|**unsubscribe** | **Boolean** |  |  [optional] |
|**templateId** | **UUID** |  |  [optional] |
|**variables** | **Map&lt;String, String&gt;** |  |  [optional] |
|**sendAt** | **OffsetDateTime** |  |  [optional] |
|**attachments** | [**List&lt;SendEmailRequestAttachmentsInner&gt;**](SendEmailRequestAttachmentsInner.md) |  |  [optional] |



