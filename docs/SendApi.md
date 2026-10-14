# SendApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**v1MessagesGet**](SendApi.md#v1MessagesGet) | **GET** /v1/messages | List outbound messages |
| [**v1MessagesIdDelete**](SendApi.md#v1MessagesIdDelete) | **DELETE** /v1/messages/{id} | Cancel a scheduled send |
| [**v1MessagesIdGet**](SendApi.md#v1MessagesIdGet) | **GET** /v1/messages/{id} | Get message status |
| [**v1MessagesStatsGet**](SendApi.md#v1MessagesStatsGet) | **GET** /v1/messages/stats | Aggregate delivery stats |
| [**v1SendBatchPost**](SendApi.md#v1SendBatchPost) | **POST** /v1/send/batch | Send a batch of emails |
| [**v1SendPost**](SendApi.md#v1SendPost) | **POST** /v1/send | Send an email |


<a id="v1MessagesGet"></a>
# **v1MessagesGet**
> V1MessagesGet200Response v1MessagesGet(status, sender, q, since, cursor, limit)

List outbound messages

Returns recent outbound messages for the calling tenant, sorted newest first. Backs the send-status pill in the SvelteKit /sends view and the outbound search box. 

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.SendApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    SendApi apiInstance = new SendApi(defaultClient);
    String status = "queued"; // String | 
    String sender = "sender_example"; // String | Exact match against the `from` mailbox.
    String q = "q_example"; // String | Free-text search across subject + sender.
    OffsetDateTime since = OffsetDateTime.now(); // OffsetDateTime | Only messages queued at or after this RFC 3339 instant.
    String cursor = "cursor_example"; // String | queued_at of the prior page boundary. Pass back the `next_cursor` returned by the previous call.
    Integer limit = 50; // Integer | 
    try {
      V1MessagesGet200Response result = apiInstance.v1MessagesGet(status, sender, q, since, cursor, limit);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling SendApi#v1MessagesGet");
      System.err.println("Status code: " + e.getCode());
      System.err.println("Reason: " + e.getResponseBody());
      System.err.println("Response headers: " + e.getResponseHeaders());
      e.printStackTrace();
    }
  }
}
```

### Parameters

| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **status** | **String**|  | [optional] [enum: queued, sending, delivered, bounced, deferred, complaint] |
| **sender** | **String**| Exact match against the &#x60;from&#x60; mailbox. | [optional] |
| **q** | **String**| Free-text search across subject + sender. | [optional] |
| **since** | **OffsetDateTime**| Only messages queued at or after this RFC 3339 instant. | [optional] |
| **cursor** | **String**| queued_at of the prior page boundary. Pass back the &#x60;next_cursor&#x60; returned by the previous call. | [optional] |
| **limit** | **Integer**|  | [optional] [default to 50] |

### Return type

[**V1MessagesGet200Response**](V1MessagesGet200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List of messages + optional next-page cursor. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

<a id="v1MessagesIdDelete"></a>
# **v1MessagesIdDelete**
> v1MessagesIdDelete(id)

Cancel a scheduled send

Cancels a still-scheduled message (future queued_at). Already sending/sent → 409.

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.SendApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    SendApi apiInstance = new SendApi(defaultClient);
    UUID id = UUID.randomUUID(); // UUID | 
    try {
      apiInstance.v1MessagesIdDelete(id);
    } catch (ApiException e) {
      System.err.println("Exception when calling SendApi#v1MessagesIdDelete");
      System.err.println("Status code: " + e.getCode());
      System.err.println("Reason: " + e.getResponseBody());
      System.err.println("Response headers: " + e.getResponseHeaders());
      e.printStackTrace();
    }
  }
}
```

### Parameters

| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **id** | **UUID**|  | |

### Return type

null (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | Cancelled. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |
| **409** | Not cancellable (already sending or sent). |  -  |

<a id="v1MessagesIdGet"></a>
# **v1MessagesIdGet**
> MessageDetail v1MessagesIdGet(id)

Get message status

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.SendApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    SendApi apiInstance = new SendApi(defaultClient);
    UUID id = UUID.randomUUID(); // UUID | 
    try {
      MessageDetail result = apiInstance.v1MessagesIdGet(id);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling SendApi#v1MessagesIdGet");
      System.err.println("Status code: " + e.getCode());
      System.err.println("Reason: " + e.getResponseBody());
      System.err.println("Response headers: " + e.getResponseHeaders());
      e.printStackTrace();
    }
  }
}
```

### Parameters

| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **id** | **UUID**|  | |

### Return type

[**MessageDetail**](MessageDetail.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Message record with the content captured at send time. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

<a id="v1MessagesStatsGet"></a>
# **v1MessagesStatsGet**
> MessageStats v1MessagesStatsGet(from, to, domain)

Aggregate delivery stats

Counts by delivery outcome (delivered/bounced/deferred/complaint) plus rates over a window, from the delivery-event store. Privacy-first: this reflects what receiving servers reported, NOT whether a human opened the mail — Lockally does no open/click tracking. 

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.SendApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    SendApi apiInstance = new SendApi(defaultClient);
    OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | Window start (default 7 days ago).
    OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | Window end (default now).
    String domain = "domain_example"; // String | Filter by sender domain.
    try {
      MessageStats result = apiInstance.v1MessagesStatsGet(from, to, domain);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling SendApi#v1MessagesStatsGet");
      System.err.println("Status code: " + e.getCode());
      System.err.println("Reason: " + e.getResponseBody());
      System.err.println("Response headers: " + e.getResponseHeaders());
      e.printStackTrace();
    }
  }
}
```

### Parameters

| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **from** | **OffsetDateTime**| Window start (default 7 days ago). | [optional] |
| **to** | **OffsetDateTime**| Window end (default now). | [optional] |
| **domain** | **String**| Filter by sender domain. | [optional] |

### Return type

[**MessageStats**](MessageStats.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Stats. |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |

<a id="v1SendBatchPost"></a>
# **v1SendBatchPost**
> V1SendBatchPost200Response v1SendBatchPost(idempotencyKey, v1SendBatchPostRequest)

Send a batch of emails

Sends up to 500 messages in one call. Each is validated and enqueued independently — a bad message fails only its own slot (partial success, HTTP 200). One &#x60;Idempotency-Key&#x60; header covers the batch; per-message keys are derived as &#x60;&lt;key&gt;:&lt;index&gt;&#x60;. 

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.SendApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    SendApi apiInstance = new SendApi(defaultClient);
    String idempotencyKey = "idempotencyKey_example"; // String | 
    V1SendBatchPostRequest v1SendBatchPostRequest = new V1SendBatchPostRequest(); // V1SendBatchPostRequest | 
    try {
      V1SendBatchPost200Response result = apiInstance.v1SendBatchPost(idempotencyKey, v1SendBatchPostRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling SendApi#v1SendBatchPost");
      System.err.println("Status code: " + e.getCode());
      System.err.println("Reason: " + e.getResponseBody());
      System.err.println("Response headers: " + e.getResponseHeaders());
      e.printStackTrace();
    }
  }
}
```

### Parameters

| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **idempotencyKey** | **String**|  | |
| **v1SendBatchPostRequest** | [**V1SendBatchPostRequest**](V1SendBatchPostRequest.md)|  | |

### Return type

[**V1SendBatchPost200Response**](V1SendBatchPost200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Per-message results (partial success). |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

<a id="v1SendPost"></a>
# **v1SendPost**
> V1SendPost200Response v1SendPost(idempotencyKey, v1SendPostRequest)

Send an email

Submits an email for delivery via lockally. Returns 202 immediately once the message is accepted into lockally&#39;s queue; the actual SMTP submission to the recipient is async. Track delivery via &#x60;GET /v1/messages/{id}&#x60; or webhook subscriptions for &#x60;delivery.delivered&#x60; / &#x60;delivery.bounced&#x60; / &#x60;delivery.complaint&#x60;.  **Idempotency-Key required.** Per design L7 — any unique string per send, 24-hour dedupe window. Repeated calls with the same key return byte-exact the original response and do NOT create a duplicate message.  **Sender authorisation.** &#x60;from&#x60; must be a non-disabled mailbox owned by the calling tenant on a verified domain. Sending from aliases is not yet supported.  **Rate cap.** Per-tenant &#x60;rate_cap_per_min&#x60; (returned on &#x60;/v1/tenant&#x60;) is enforced — 429 with &#x60;Retry-After: 60&#x60; once tripped.  **Recipient warning.** Over 25 total recipients (To+Cc+Bcc) sets a &#x60;warning&#x60; field in the response — large fan-outs queue noticeably at scale. Hard cap is 100/send.  **Not every success is a 202.** Check the status code, not just the body. A &#x60;200&#x60; means nothing was queued: either every recipient was already suppressed, or the call used a test key and the send was simulated. Both are successes, and neither produces a real delivery. See the &#x60;200&#x60; response below.  **Warm-up headers.** While the platform is in its outbound warm-up ramp, accepted sends carry &#x60;X-Warmup-Day&#x60;, &#x60;X-Warmup-Daily-Cap&#x60; and &#x60;X-Warmup-Used-Today&#x60;. They describe a platform-wide cap shared by every tenant, not your own allowance, and they disappear once the ramp finishes. Hitting the cap returns 429. 

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.SendApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    SendApi apiInstance = new SendApi(defaultClient);
    String idempotencyKey = "idempotencyKey_example"; // String | 
    V1SendPostRequest v1SendPostRequest = new V1SendPostRequest(); // V1SendPostRequest | 
    try {
      V1SendPost200Response result = apiInstance.v1SendPost(idempotencyKey, v1SendPostRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling SendApi#v1SendPost");
      System.err.println("Status code: " + e.getCode());
      System.err.println("Reason: " + e.getResponseBody());
      System.err.println("Response headers: " + e.getResponseHeaders());
      e.printStackTrace();
    }
  }
}
```

### Parameters

| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **idempotencyKey** | **String**|  | |
| **v1SendPostRequest** | [**V1SendPostRequest**](V1SendPostRequest.md)|  | |

### Return type

[**V1SendPost200Response**](V1SendPost200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Accepted, but nothing was queued for real delivery. Two cases, told apart by &#x60;status&#x60;:  - &#x60;suppressed&#x60; — every recipient was on your suppression list, so   the send was dropped. Deliberately a success, not a retryable   error: retrying cannot change the outcome. There is no &#x60;id&#x60; or   &#x60;message_id&#x60;, because no message was created. Complaint and   bounce suppressions block every send; unsubscribe and manual   suppressions block only opt-in sends (&#x60;unsubscribe: true&#x60;). - &#x60;delivered&#x60; — the call used a test key (&#x60;lk_test_&#x60;). The message   is recorded and a &#x60;delivery.delivered&#x60; webhook fires with a   simulated &#x60;250 OK&#x60;, but nothing leaves the platform. Test sends   count against nothing: not your rate cap, allowance, send units,   the warm-up ramp, or your reputation.  |  -  |
| **202** | Queued for delivery. |  * Idempotent-Replay - \&quot;true\&quot; when the response is replayed from the idempotency cache. <br>  * X-Warmup-Day - Present only during the platform&#39;s outbound warm-up ramp: which day of the ramp this send landed on. <br>  * X-Warmup-Daily-Cap - Warm-up ramp only: total messages the whole platform may send today, shared across all tenants. <br>  * X-Warmup-Used-Today - Warm-up ramp only: how much of that platform-wide cap was already used when this send was accepted. <br>  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **429** | Rate limited. Either your per-tenant &#x60;rate_cap_per_min&#x60;, or the platform-wide warm-up cap for the day (which resets at UTC midnight, so &#x60;Retry-After&#x60; can be hours rather than 60 seconds).  |  * Retry-After - 60 for the per-tenant cap; seconds until UTC midnight when the warm-up cap is what was hit. <br>  |

