# BillingApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createBillingCheckout**](BillingApi.md#createBillingCheckout) | **POST** /v1/billing/checkout | Create a plan checkout session |
| [**createUnitsCheckout**](BillingApi.md#createUnitsCheckout) | **POST** /v1/billing/units/checkout | Create a send-units checkout session |
| [**getBilling**](BillingApi.md#getBilling) | **GET** /v1/billing | Get billing status |


<a id="createBillingCheckout"></a>
# **createBillingCheckout**
> CreateBillingCheckout200Response createBillingCheckout(createBillingCheckoutRequest)

Create a plan checkout session

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.BillingApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    BillingApi apiInstance = new BillingApi(defaultClient);
    CreateBillingCheckoutRequest createBillingCheckoutRequest = new CreateBillingCheckoutRequest(); // CreateBillingCheckoutRequest | 
    try {
      CreateBillingCheckout200Response result = apiInstance.createBillingCheckout(createBillingCheckoutRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling BillingApi#createBillingCheckout");
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
| **createBillingCheckoutRequest** | [**CreateBillingCheckoutRequest**](CreateBillingCheckoutRequest.md)|  | |

### Return type

[**CreateBillingCheckout200Response**](CreateBillingCheckout200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Checkout URL for payment. |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **503** | Service is temporarily unable to handle the request (e.g. database unreachable). |  -  |

<a id="createUnitsCheckout"></a>
# **createUnitsCheckout**
> CreateUnitsCheckout200Response createUnitsCheckout(createUnitsCheckoutRequest)

Create a send-units checkout session

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.BillingApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    BillingApi apiInstance = new BillingApi(defaultClient);
    CreateUnitsCheckoutRequest createUnitsCheckoutRequest = new CreateUnitsCheckoutRequest(); // CreateUnitsCheckoutRequest | 
    try {
      CreateUnitsCheckout200Response result = apiInstance.createUnitsCheckout(createUnitsCheckoutRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling BillingApi#createUnitsCheckout");
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
| **createUnitsCheckoutRequest** | [**CreateUnitsCheckoutRequest**](CreateUnitsCheckoutRequest.md)|  | |

### Return type

[**CreateUnitsCheckout200Response**](CreateUnitsCheckout200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Checkout URL for the selected unit bundle. |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **503** | Service is temporarily unable to handle the request (e.g. database unreachable). |  -  |

<a id="getBilling"></a>
# **getBilling**
> BillingStatus getBilling()

Get billing status

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.BillingApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    BillingApi apiInstance = new BillingApi(defaultClient);
    try {
      BillingStatus result = apiInstance.getBilling();
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling BillingApi#getBilling");
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

[**BillingStatus**](BillingStatus.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Current billing status. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

