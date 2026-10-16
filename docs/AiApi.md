# AiApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**classifyThread**](AiApi.md#classifyThread) | **POST** /v1/threads/{threadID}/classify | LLM-classify a thread |
| [**createAiUnitsCheckout**](AiApi.md#createAiUnitsCheckout) | **POST** /v1/billing/ai-units/checkout | Buy prepaid AI units |
| [**getAiConfig**](AiApi.md#getAiConfig) | **GET** /v1/ai-config | Read the tenant&#39;s AI configuration |
| [**updateAiConfig**](AiApi.md#updateAiConfig) | **PUT** /v1/ai-config | Configure the AI tier |


<a id="classifyThread"></a>
# **classifyThread**
> ThreadClassification classifyThread(threadID, refresh)

LLM-classify a thread

Returns {intent, urgency, summary, suggested_action} via the tenant&#39;s AI tier (BYOK or prepaid units, see /v1/ai-config). Cached per thread state: unchanged threads return the cache free; ?refresh&#x3D;true forces a re-run. A failed model call charges nothing. 402 when the AI tier is off.

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
      ThreadClassification result = apiInstance.classifyThread(threadID, refresh);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling AiApi#classifyThread");
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

[**ThreadClassification**](ThreadClassification.md)

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

<a id="createAiUnitsCheckout"></a>
# **createAiUnitsCheckout**
> CreateAiUnitsCheckout200Response createAiUnitsCheckout()

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
      CreateAiUnitsCheckout200Response result = apiInstance.createAiUnitsCheckout();
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling AiApi#createAiUnitsCheckout");
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

[**CreateAiUnitsCheckout200Response**](CreateAiUnitsCheckout200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paystack authorization URL for the selected AI unit bundle. |  -  |

<a id="getAiConfig"></a>
# **getAiConfig**
> AiConfig getAiConfig()

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
      AiConfig result = apiInstance.getAiConfig();
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling AiApi#getAiConfig");
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

[**AiConfig**](AiConfig.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | AI config |  -  |

<a id="updateAiConfig"></a>
# **updateAiConfig**
> AiConfigUpdate updateAiConfig()

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
      AiConfigUpdate result = apiInstance.updateAiConfig();
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling AiApi#updateAiConfig");
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

[**AiConfigUpdate**](AiConfigUpdate.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Applied |  -  |

