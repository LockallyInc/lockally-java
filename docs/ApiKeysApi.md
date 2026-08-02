# ApiKeysApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**v1ApiKeysGet**](ApiKeysApi.md#v1ApiKeysGet) | **GET** /v1/api-keys | List API keys |
| [**v1ApiKeysIdDelete**](ApiKeysApi.md#v1ApiKeysIdDelete) | **DELETE** /v1/api-keys/{id} | Revoke an API key |
| [**v1ApiKeysPost**](ApiKeysApi.md#v1ApiKeysPost) | **POST** /v1/api-keys | Create an API key |


<a id="v1ApiKeysGet"></a>
# **v1ApiKeysGet**
> V1ApiKeysGet200Response v1ApiKeysGet()

List API keys

Returns all API keys (active and revoked) belonging to the calling tenant. The &#x60;secret&#x60; is **never** returned — only prefix + metadata. 

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.ApiKeysApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    ApiKeysApi apiInstance = new ApiKeysApi(defaultClient);
    try {
      V1ApiKeysGet200Response result = apiInstance.v1ApiKeysGet();
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling ApiKeysApi#v1ApiKeysGet");
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

[**V1ApiKeysGet200Response**](V1ApiKeysGet200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Key list |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

<a id="v1ApiKeysIdDelete"></a>
# **v1ApiKeysIdDelete**
> v1ApiKeysIdDelete(id)

Revoke an API key

Soft-deletes (sets &#x60;revoked_at&#x60;) on the named key. The row stays for audit purposes; the key no longer authenticates.  You **cannot revoke the key currently being used** to make this call — that would lock you out. Use a different &#x60;tenant:admin&#x60; key. 

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.ApiKeysApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    ApiKeysApi apiInstance = new ApiKeysApi(defaultClient);
    UUID id = UUID.randomUUID(); // UUID | 
    try {
      apiInstance.v1ApiKeysIdDelete(id);
    } catch (ApiException e) {
      System.err.println("Exception when calling ApiKeysApi#v1ApiKeysIdDelete");
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
| **204** | Revoked. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |
| **409** | Refused — key is the one in use for this request. |  -  |

<a id="v1ApiKeysPost"></a>
# **v1ApiKeysPost**
> V1ApiKeysPost201Response v1ApiKeysPost(v1ApiKeysPostRequest)

Create an API key

Provisions a fresh API key for the calling tenant.  **The full &#x60;secret&#x60; is included in this response ONLY** — store it immediately. The cleartext secret is not recoverable from the argon2id hash kept server-side; rotate by creating a new key and revoking the old one. 

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.ApiKeysApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    ApiKeysApi apiInstance = new ApiKeysApi(defaultClient);
    V1ApiKeysPostRequest v1ApiKeysPostRequest = new V1ApiKeysPostRequest(); // V1ApiKeysPostRequest | 
    try {
      V1ApiKeysPost201Response result = apiInstance.v1ApiKeysPost(v1ApiKeysPostRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling ApiKeysApi#v1ApiKeysPost");
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
| **v1ApiKeysPostRequest** | [**V1ApiKeysPostRequest**](V1ApiKeysPostRequest.md)|  | |

### Return type

[**V1ApiKeysPost201Response**](V1ApiKeysPost201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Key created — &#x60;secret&#x60; is in the response and shown only here. |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

