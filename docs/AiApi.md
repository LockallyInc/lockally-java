# AiApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**v1AiConfigGet**](AiApi.md#v1AiConfigGet) | **GET** /v1/ai-config | Read the tenant&#39;s AI configuration |
| [**v1AiConfigPut**](AiApi.md#v1AiConfigPut) | **PUT** /v1/ai-config | Configure the AI tier |
| [**v1BillingAiUnitsCheckoutPost**](AiApi.md#v1BillingAiUnitsCheckoutPost) | **POST** /v1/billing/ai-units/checkout | Buy prepaid AI units |
| [**v1ThreadsThreadIDClassifyPost**](AiApi.md#v1ThreadsThreadIDClassifyPost) | **POST** /v1/threads/{threadID}/classify | LLM-classify a thread |


<a id="v1AiConfigGet"></a>
# **v1AiConfigGet**
> Object v1AiConfigGet()

Read the tenant&#39;s AI configuration

Mode (off/byok/units), model, masked key hint, AI-unit balance, whether the units tier is available on this deployment.

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.AiApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    AiApi apiInstance = new AiApi(defaultClient);
    try {
      Object result = apiInstance.v1AiConfigGet();
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling AiApi#v1AiConfigGet");
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

**Object**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | AI config |  -  |

<a id="v1AiConfigPut"></a>
# **v1AiConfigPut**
> Object v1AiConfigPut()

Configure the AI tier

Body: {\&quot;mode\&quot;: \&quot;off|byok|units\&quot;, \&quot;model\&quot;: \&quot;...\&quot;, \&quot;anthropic_key\&quot;: \&quot;sk-ant-...\&quot;}. BYOK keys are stored AES-256-GCM encrypted; the cleartext is never returned. Omit anthropic_key to keep the stored one.

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.AiApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    AiApi apiInstance = new AiApi(defaultClient);
    try {
      Object result = apiInstance.v1AiConfigPut();
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling AiApi#v1AiConfigPut");
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

**Object**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Applied |  -  |

<a id="v1BillingAiUnitsCheckoutPost"></a>
# **v1BillingAiUnitsCheckoutPost**
> Object v1BillingAiUnitsCheckoutPost()

Buy prepaid AI units

Body: {\&quot;bundle\&quot;: \&quot;100|500|2000\&quot;}. One classification &#x3D; one unit; bundles expire after 6 months. Admin session required. 503 until Paystack billing is configured.

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.AiApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    AiApi apiInstance = new AiApi(defaultClient);
    try {
      Object result = apiInstance.v1BillingAiUnitsCheckoutPost();
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling AiApi#v1BillingAiUnitsCheckoutPost");
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

**Object**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paystack authorization URL |  -  |

<a id="v1ThreadsThreadIDClassifyPost"></a>
# **v1ThreadsThreadIDClassifyPost**
> Object v1ThreadsThreadIDClassifyPost(threadID, refresh)

LLM-classify a thread

Returns {intent, urgency, summary, suggested_action} via the tenant&#39;s AI tier (BYOK or prepaid units — see /v1/ai-config). Cached per thread state: unchanged threads return the cache free; ?refresh&#x3D;true forces a re-run. A failed model call charges nothing. 402 when the AI tier is off.

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.AiApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    AiApi apiInstance = new AiApi(defaultClient);
    UUID threadID = UUID.randomUUID(); // UUID | 
    Boolean refresh = true; // Boolean | 
    try {
      Object result = apiInstance.v1ThreadsThreadIDClassifyPost(threadID, refresh);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling AiApi#v1ThreadsThreadIDClassifyPost");
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
| **threadID** | **UUID**|  | |
| **refresh** | **Boolean**|  | [optional] |

### Return type

**Object**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Classification |  -  |
| **402** | AI tier not enabled / out of units |  -  |

