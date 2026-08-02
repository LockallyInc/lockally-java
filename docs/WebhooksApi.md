# WebhooksApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**v1WebhooksGet**](WebhooksApi.md#v1WebhooksGet) | **GET** /v1/webhooks | List webhooks |
| [**v1WebhooksIdDelete**](WebhooksApi.md#v1WebhooksIdDelete) | **DELETE** /v1/webhooks/{id} | Delete a webhook |
| [**v1WebhooksIdPatch**](WebhooksApi.md#v1WebhooksIdPatch) | **PATCH** /v1/webhooks/{id} | Update a webhook |
| [**v1WebhooksPost**](WebhooksApi.md#v1WebhooksPost) | **POST** /v1/webhooks | Create a webhook |


<a id="v1WebhooksGet"></a>
# **v1WebhooksGet**
> V1WebhooksGet200Response v1WebhooksGet()

List webhooks

Returns the calling tenant&#39;s webhook subscriptions. Never returns the signing secret — only metadata. 

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.WebhooksApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    WebhooksApi apiInstance = new WebhooksApi(defaultClient);
    try {
      V1WebhooksGet200Response result = apiInstance.v1WebhooksGet();
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling WebhooksApi#v1WebhooksGet");
      System.err.println("Status code: " + e.getCode());
      System.err.println("Reason: " + e.getResponseBody());
      System.err.println("Response headers: " + e.getResponseHeaders());
      e.printStackTrace();
    }
  }
}
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**V1WebhooksGet200Response**](V1WebhooksGet200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Webhook list. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

<a id="v1WebhooksIdDelete"></a>
# **v1WebhooksIdDelete**
> v1WebhooksIdDelete(id)

Delete a webhook

Hard-delete; cascades to &#x60;webhook_deliveries&#x60; history.

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.WebhooksApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    WebhooksApi apiInstance = new WebhooksApi(defaultClient);
    UUID id = UUID.randomUUID(); // UUID | 
    try {
      apiInstance.v1WebhooksIdDelete(id);
    } catch (ApiException e) {
      System.err.println("Exception when calling WebhooksApi#v1WebhooksIdDelete");
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
| **204** | Deleted. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

<a id="v1WebhooksIdPatch"></a>
# **v1WebhooksIdPatch**
> Webhook v1WebhooksIdPatch(id, v1WebhooksIdPatchRequest)

Update a webhook

Supply at least one of &#x60;url&#x60;, &#x60;events&#x60;, &#x60;paused&#x60;. Setting &#x60;paused&#x60; to &#x60;false&#x60; ALSO resets &#x60;consecutive_failures&#x60; to 0 — re-arms the 50-failure auto-pause counter. 

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.WebhooksApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    WebhooksApi apiInstance = new WebhooksApi(defaultClient);
    UUID id = UUID.randomUUID(); // UUID | 
    V1WebhooksIdPatchRequest v1WebhooksIdPatchRequest = new V1WebhooksIdPatchRequest(); // V1WebhooksIdPatchRequest | 
    try {
      Webhook result = apiInstance.v1WebhooksIdPatch(id, v1WebhooksIdPatchRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling WebhooksApi#v1WebhooksIdPatch");
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
| **v1WebhooksIdPatchRequest** | [**V1WebhooksIdPatchRequest**](V1WebhooksIdPatchRequest.md)|  | |

### Return type

[**Webhook**](Webhook.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Updated webhook. |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

<a id="v1WebhooksPost"></a>
# **v1WebhooksPost**
> Webhook v1WebhooksPost(v1WebhooksPostRequest)

Create a webhook

Subscribes a URL to one or more event types. Returns the &#x60;signing_secret&#x60; ONCE in the response — store it immediately. The dispatcher signs every outbound POST per design L3:      X-Lockally-Signature: t&#x3D;&lt;unix&gt;,v1&#x3D;&lt;hex(hmac_sha256(secret, t + \&quot;.\&quot; + body))&gt;  Verify on your end using HMAC-SHA256 with a 5-minute timestamp window (replay protection). A reference verifier ships in [internal/webhook](https://github.com/ucheigwedinma/lockally/blob/main/internal/webhook/sign.go).  Event names: see the [event catalogue](https://github.com/ucheigwedinma/lockally/blob/main/docs/v1-design.md#64-webhook-event-catalogue-v1). 

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.WebhooksApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    WebhooksApi apiInstance = new WebhooksApi(defaultClient);
    V1WebhooksPostRequest v1WebhooksPostRequest = new V1WebhooksPostRequest(); // V1WebhooksPostRequest | 
    try {
      Webhook result = apiInstance.v1WebhooksPost(v1WebhooksPostRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling WebhooksApi#v1WebhooksPost");
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
| **v1WebhooksPostRequest** | [**V1WebhooksPostRequest**](V1WebhooksPostRequest.md)|  | |

### Return type

[**Webhook**](Webhook.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Created. &#x60;signing_secret&#x60; is in the response ONLY here. |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

