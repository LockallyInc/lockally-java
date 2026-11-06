

# SendEmailBatchRequest


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**messages** | [**List&lt;SendMessage&gt;**](SendMessage.md) |  |  |
|**variables** | **Map&lt;String, String&gt;** | Template variables every message in the batch inherits. Each message&#39;s own &#x60;variables&#x60; override these key by key, so shared values are written once and per-recipient ones stay per-recipient.  Without this, a 500-message batch repeats every shared variable 500 times: most of the payload, and 500 places for one of them to differ by a typo.  |  [optional] |



