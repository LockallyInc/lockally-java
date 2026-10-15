# DistributionListsApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createDistributionList**](DistributionListsApi.md#createDistributionList) | **POST** /v1/distribution-lists | Create a distribution list |
| [**deleteDistributionList**](DistributionListsApi.md#deleteDistributionList) | **DELETE** /v1/distribution-lists/{address} | Delete a distribution list |
| [**getDistributionList**](DistributionListsApi.md#getDistributionList) | **GET** /v1/distribution-lists/{address} | Get a distribution list |
| [**listDistributionLists**](DistributionListsApi.md#listDistributionLists) | **GET** /v1/distribution-lists | List distribution lists |
| [**replaceDistributionListMembers**](DistributionListsApi.md#replaceDistributionListMembers) | **PUT** /v1/distribution-lists/{address}/members | Replace distribution list members |


<a id="createDistributionList"></a>
# **createDistributionList**
> DistributionListDetail createDistributionList(createDistributionListRequest)

Create a distribution list

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.DistributionListsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    DistributionListsApi apiInstance = new DistributionListsApi(defaultClient);
    CreateDistributionListRequest createDistributionListRequest = new CreateDistributionListRequest(); // CreateDistributionListRequest | 
    try {
      DistributionListDetail result = apiInstance.createDistributionList(createDistributionListRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling DistributionListsApi#createDistributionList");
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
| **createDistributionListRequest** | [**CreateDistributionListRequest**](CreateDistributionListRequest.md)|  | |

### Return type

[**DistributionListDetail**](DistributionListDetail.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Distribution list created. |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **409** | List address already exists. |  -  |

<a id="deleteDistributionList"></a>
# **deleteDistributionList**
> deleteDistributionList(address)

Delete a distribution list

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.DistributionListsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    DistributionListsApi apiInstance = new DistributionListsApi(defaultClient);
    String address = "address_example"; // String | Distribution list email address
    try {
      apiInstance.deleteDistributionList(address);
    } catch (ApiException e) {
      System.err.println("Exception when calling DistributionListsApi#deleteDistributionList");
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
| **address** | **String**| Distribution list email address | |

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
| **204** | No content |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

<a id="getDistributionList"></a>
# **getDistributionList**
> DistributionListDetail getDistributionList(address)

Get a distribution list

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.DistributionListsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    DistributionListsApi apiInstance = new DistributionListsApi(defaultClient);
    String address = "address_example"; // String | Distribution list email address
    try {
      DistributionListDetail result = apiInstance.getDistributionList(address);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling DistributionListsApi#getDistributionList");
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
| **address** | **String**| Distribution list email address | |

### Return type

[**DistributionListDetail**](DistributionListDetail.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Distribution list with full member list. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

<a id="listDistributionLists"></a>
# **listDistributionLists**
> ListDistributionLists200Response listDistributionLists()

List distribution lists

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.DistributionListsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    DistributionListsApi apiInstance = new DistributionListsApi(defaultClient);
    try {
      ListDistributionLists200Response result = apiInstance.listDistributionLists();
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling DistributionListsApi#listDistributionLists");
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

[**ListDistributionLists200Response**](ListDistributionLists200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | All distribution lists for the tenant. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

<a id="replaceDistributionListMembers"></a>
# **replaceDistributionListMembers**
> ReplaceDistributionListMembers200Response replaceDistributionListMembers(address, replaceDistributionListMembersRequest)

Replace distribution list members

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.DistributionListsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    DistributionListsApi apiInstance = new DistributionListsApi(defaultClient);
    String address = "address_example"; // String | Distribution list email address
    ReplaceDistributionListMembersRequest replaceDistributionListMembersRequest = new ReplaceDistributionListMembersRequest(); // ReplaceDistributionListMembersRequest | 
    try {
      ReplaceDistributionListMembers200Response result = apiInstance.replaceDistributionListMembers(address, replaceDistributionListMembersRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling DistributionListsApi#replaceDistributionListMembers");
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
| **address** | **String**| Distribution list email address | |
| **replaceDistributionListMembersRequest** | [**ReplaceDistributionListMembersRequest**](ReplaceDistributionListMembersRequest.md)|  | |

### Return type

[**ReplaceDistributionListMembers200Response**](ReplaceDistributionListMembers200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Updated member list. |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

