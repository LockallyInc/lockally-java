# IpPoolsApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createDedicatedIPRequest**](IpPoolsApi.md#createDedicatedIPRequest) | **POST** /v1/dedicated-ip-requests | Request a dedicated IP |
| [**getIPAssignment**](IpPoolsApi.md#getIPAssignment) | **GET** /v1/ip-assignment | Get current IP assignment |
| [**listDedicatedIPRequests**](IpPoolsApi.md#listDedicatedIPRequests) | **GET** /v1/dedicated-ip-requests | List dedicated IP requests |


<a id="createDedicatedIPRequest"></a>
# **createDedicatedIPRequest**
> DedicatedIPRequest createDedicatedIPRequest(createDedicatedIPRequestRequest)

Request a dedicated IP

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.IpPoolsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    IpPoolsApi apiInstance = new IpPoolsApi(defaultClient);
    CreateDedicatedIPRequestRequest createDedicatedIPRequestRequest = new CreateDedicatedIPRequestRequest(); // CreateDedicatedIPRequestRequest | 
    try {
      DedicatedIPRequest result = apiInstance.createDedicatedIPRequest(createDedicatedIPRequestRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling IpPoolsApi#createDedicatedIPRequest");
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
| **createDedicatedIPRequestRequest** | [**CreateDedicatedIPRequestRequest**](CreateDedicatedIPRequestRequest.md)|  | |

### Return type

[**DedicatedIPRequest**](DedicatedIPRequest.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Dedicated IP request submitted. |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **409** | A pending request already exists. |  -  |

<a id="getIPAssignment"></a>
# **getIPAssignment**
> GetIPAssignment200Response getIPAssignment()

Get current IP assignment

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.IpPoolsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    IpPoolsApi apiInstance = new IpPoolsApi(defaultClient);
    try {
      GetIPAssignment200Response result = apiInstance.getIPAssignment();
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling IpPoolsApi#getIPAssignment");
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

[**GetIPAssignment200Response**](GetIPAssignment200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The tenant&#39;s current outbound IP assignment. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

<a id="listDedicatedIPRequests"></a>
# **listDedicatedIPRequests**
> ListDedicatedIPRequests200Response listDedicatedIPRequests()

List dedicated IP requests

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.IpPoolsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    IpPoolsApi apiInstance = new IpPoolsApi(defaultClient);
    try {
      ListDedicatedIPRequests200Response result = apiInstance.listDedicatedIPRequests();
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling IpPoolsApi#listDedicatedIPRequests");
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

[**ListDedicatedIPRequests200Response**](ListDedicatedIPRequests200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Dedicated IP request history. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

