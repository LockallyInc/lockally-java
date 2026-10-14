

# SendMessage


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**from** | **String** |  |  |
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
|**attachments** | [**List&lt;V1SendPostRequestAttachmentsInner&gt;**](V1SendPostRequestAttachmentsInner.md) |  |  [optional] |



