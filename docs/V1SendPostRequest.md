

# V1SendPostRequest


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**from** | **String** |  |  |
|**to** | **List&lt;String&gt;** |  |  |
|**cc** | **List&lt;String&gt;** |  |  [optional] |
|**bcc** | **List&lt;String&gt;** |  |  [optional] |
|**subject** | **String** |  |  [optional] |
|**text** | **String** | Plain-text body. Required if &#x60;html&#x60; is absent. |  [optional] |
|**html** | **String** | HTML body. Required if &#x60;text&#x60; is absent. |  [optional] |
|**headers** | **Map&lt;String, String&gt;** |  |  [optional] |
|**unsubscribe** | **Boolean** | Mark as opt-in/broadcast: skips suppressed recipients and adds a managed one-click List-Unsubscribe header. |  [optional] |
|**templateId** | **UUID** | Render subject/text/html from a stored template (GET /v1/templates). Mutually exclusive with inline subject/text/html. |  [optional] |
|**variables** | **Map&lt;String, String&gt;** | Values substituted into the template&#39;s {{variable}} placeholders. |  [optional] |
|**sendAt** | **OffsetDateTime** | Schedule delivery for a future RFC3339 time (≤ 30 days out). Omit or past &#x3D; send now. Cancel with DELETE /v1/messages/{id} while scheduled. |  [optional] |
|**attachments** | [**List&lt;V1SendPostRequestAttachmentsInner&gt;**](V1SendPostRequestAttachmentsInner.md) |  |  [optional] |



