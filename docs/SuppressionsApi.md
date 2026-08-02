# SuppressionsApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**v1SuppressionsEmailDelete**](SuppressionsApi.md#v1SuppressionsEmailDelete) | **DELETE** /v1/suppressions/{email} | Remove a suppression |
| [**v1SuppressionsEmailGet**](SuppressionsApi.md#v1SuppressionsEmailGet) | **GET** /v1/suppressions/{email} | Check whether an address is suppressed |
| [**v1SuppressionsGet**](SuppressionsApi.md#v1SuppressionsGet) | **GET** /v1/suppressions | List suppressed recipients |
| [**v1SuppressionsPost**](SuppressionsApi.md#v1SuppressionsPost) | **POST** /v1/suppressions | Add a suppression |


<a id="v1SuppressionsEmailDelete"></a>
# **v1SuppressionsEmailDelete**
> v1SuppressionsEmailDelete(email)

Remove a suppression

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.SuppressionsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    SuppressionsApi apiInstance = new SuppressionsApi(defaultClient);
    String email = "email_example"; // String | 
    try {
      apiInstance.v1SuppressionsEmailDelete(email);
    } catch (ApiException e) {
      System.err.println("Exception when calling SuppressionsApi#v1SuppressionsEmailDelete");
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
| **email** | **String**|  | |

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
| **204** | Removed. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

<a id="v1SuppressionsEmailGet"></a>
# **v1SuppressionsEmailGet**
> Suppression v1SuppressionsEmailGet(email)

Check whether an address is suppressed

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.SuppressionsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    SuppressionsApi apiInstance = new SuppressionsApi(defaultClient);
    String email = "email_example"; // String | 
    try {
      Suppression result = apiInstance.v1SuppressionsEmailGet(email);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling SuppressionsApi#v1SuppressionsEmailGet");
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
| **email** | **String**|  | |

### Return type

[**Suppression**](Suppression.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Suppressed. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

<a id="v1SuppressionsGet"></a>
# **v1SuppressionsGet**
> V1SuppressionsGet200Response v1SuppressionsGet(reason, cursor, limit)

List suppressed recipients

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.SuppressionsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    SuppressionsApi apiInstance = new SuppressionsApi(defaultClient);
    String reason = "unsubscribe"; // String | 
    String cursor = "cursor_example"; // String | 
    Integer limit = 50; // Integer | 
    try {
      V1SuppressionsGet200Response result = apiInstance.v1SuppressionsGet(reason, cursor, limit);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling SuppressionsApi#v1SuppressionsGet");
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
| **reason** | **String**|  | [optional] [enum: unsubscribe, complaint, bounce, manual] |
| **cursor** | **String**|  | [optional] |
| **limit** | **Integer**|  | [optional] [default to 50] |

### Return type

[**V1SuppressionsGet200Response**](V1SuppressionsGet200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Suppressions. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |

<a id="v1SuppressionsPost"></a>
# **v1SuppressionsPost**
> Suppression v1SuppressionsPost(v1SuppressionsPostRequest)

Add a suppression

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.SuppressionsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    SuppressionsApi apiInstance = new SuppressionsApi(defaultClient);
    V1SuppressionsPostRequest v1SuppressionsPostRequest = new V1SuppressionsPostRequest(); // V1SuppressionsPostRequest | 
    try {
      Suppression result = apiInstance.v1SuppressionsPost(v1SuppressionsPostRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling SuppressionsApi#v1SuppressionsPost");
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
| **v1SuppressionsPostRequest** | [**V1SuppressionsPostRequest**](V1SuppressionsPostRequest.md)|  | |

### Return type

[**Suppression**](Suppression.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Added. |  -  |
| **400** | Malformed request. |  -  |

