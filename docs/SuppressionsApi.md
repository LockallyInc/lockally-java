# SuppressionsApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createSuppression**](SuppressionsApi.md#createSuppression) | **POST** /v1/suppressions | Add a suppression |
| [**deleteSuppression**](SuppressionsApi.md#deleteSuppression) | **DELETE** /v1/suppressions/{email} | Remove a suppression |
| [**getSuppression**](SuppressionsApi.md#getSuppression) | **GET** /v1/suppressions/{email} | Check whether an address is suppressed |
| [**listSuppressions**](SuppressionsApi.md#listSuppressions) | **GET** /v1/suppressions | List suppressed recipients |


<a id="createSuppression"></a>
# **createSuppression**
> Suppression createSuppression(createSuppressionRequest)

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
    CreateSuppressionRequest createSuppressionRequest = new CreateSuppressionRequest(); // CreateSuppressionRequest | 
    try {
      Suppression result = apiInstance.createSuppression(createSuppressionRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling SuppressionsApi#createSuppression");
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
| **createSuppressionRequest** | [**CreateSuppressionRequest**](CreateSuppressionRequest.md)|  | |

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

<a id="deleteSuppression"></a>
# **deleteSuppression**
> deleteSuppression(email)

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
      apiInstance.deleteSuppression(email);
    } catch (ApiException e) {
      System.err.println("Exception when calling SuppressionsApi#deleteSuppression");
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

<a id="getSuppression"></a>
# **getSuppression**
> Suppression getSuppression(email)

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
      Suppression result = apiInstance.getSuppression(email);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling SuppressionsApi#getSuppression");
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

<a id="listSuppressions"></a>
# **listSuppressions**
> ListSuppressions200Response listSuppressions(reason, cursor, limit)

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
      ListSuppressions200Response result = apiInstance.listSuppressions(reason, cursor, limit);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling SuppressionsApi#listSuppressions");
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

[**ListSuppressions200Response**](ListSuppressions200Response.md)

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

