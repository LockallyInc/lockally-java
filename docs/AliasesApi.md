# AliasesApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**v1AliasesAddressDelete**](AliasesApi.md#v1AliasesAddressDelete) | **DELETE** /v1/aliases/{address} | Delete an alias |
| [**v1AliasesGet**](AliasesApi.md#v1AliasesGet) | **GET** /v1/aliases | List aliases |
| [**v1AliasesPost**](AliasesApi.md#v1AliasesPost) | **POST** /v1/aliases | Create an alias |


<a id="v1AliasesAddressDelete"></a>
# **v1AliasesAddressDelete**
> v1AliasesAddressDelete(address)

Delete an alias

Hard-delete (no soft-delete window — aliases are cheap to recreate).

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.AliasesApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    AliasesApi apiInstance = new AliasesApi(defaultClient);
    String address = "address_example"; // String | 
    try {
      apiInstance.v1AliasesAddressDelete(address);
    } catch (ApiException e) {
      System.err.println("Exception when calling AliasesApi#v1AliasesAddressDelete");
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
| **address** | **String**|  | |

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

<a id="v1AliasesGet"></a>
# **v1AliasesGet**
> V1AliasesGet200Response v1AliasesGet()

List aliases

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.AliasesApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    AliasesApi apiInstance = new AliasesApi(defaultClient);
    try {
      V1AliasesGet200Response result = apiInstance.v1AliasesGet();
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling AliasesApi#v1AliasesGet");
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

[**V1AliasesGet200Response**](V1AliasesGet200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Alias list. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

<a id="v1AliasesPost"></a>
# **v1AliasesPost**
> Alias v1AliasesPost(v1AliasesPostRequest)

Create an alias

Creates an email alias. &#x60;alias_address&#x60; must be on a verified tenant-owned domain. &#x60;alias_target&#x60; can be any email — intra-tenant or external (forwarding to a Gmail account is a legitimate use). 

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.AliasesApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    AliasesApi apiInstance = new AliasesApi(defaultClient);
    V1AliasesPostRequest v1AliasesPostRequest = new V1AliasesPostRequest(); // V1AliasesPostRequest | 
    try {
      Alias result = apiInstance.v1AliasesPost(v1AliasesPostRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling AliasesApi#v1AliasesPost");
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
| **v1AliasesPostRequest** | [**V1AliasesPostRequest**](V1AliasesPostRequest.md)|  | |

### Return type

[**Alias**](Alias.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Alias created. |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **409** | Alias address already exists. |  -  |

