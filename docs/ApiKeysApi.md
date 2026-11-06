# ApiKeysApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createApiKey**](ApiKeysApi.md#createApiKey) | **POST** /v1/api-keys | Create an API key |
| [**listApiKeys**](ApiKeysApi.md#listApiKeys) | **GET** /v1/api-keys | List API keys |
| [**revokeApiKey**](ApiKeysApi.md#revokeApiKey) | **DELETE** /v1/api-keys/{id} | Revoke an API key |
| [**rotateApiKey**](ApiKeysApi.md#rotateApiKey) | **POST** /v1/api-keys/{id}/rotate | Rotate an API key |
| [**updateApiKey**](ApiKeysApi.md#updateApiKey) | **PATCH** /v1/api-keys/{id} | Update an API key |


<a id="createApiKey"></a>
# **createApiKey**
> CreateApiKey201Response createApiKey(createApiKeyRequest)

Create an API key

Provisions a fresh API key for the calling tenant.  **The full &#x60;secret&#x60; is included in this response ONLY**, store it immediately. The cleartext secret is not recoverable from the argon2id hash kept server-side; rotate by creating a new key and revoking the old one. 

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
    CreateApiKeyRequest createApiKeyRequest = new CreateApiKeyRequest(); // CreateApiKeyRequest | 
    try {
      CreateApiKey201Response result = apiInstance.createApiKey(createApiKeyRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling ApiKeysApi#createApiKey");
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
| **createApiKeyRequest** | [**CreateApiKeyRequest**](CreateApiKeyRequest.md)|  | |

### Return type

[**CreateApiKey201Response**](CreateApiKey201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Key created, &#x60;secret&#x60; is in the response and shown only here. |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

<a id="listApiKeys"></a>
# **listApiKeys**
> ListApiKeys200Response listApiKeys(sort, order)

List API keys

Returns all API keys (active and revoked) belonging to the calling tenant. The &#x60;secret&#x60; is **never** returned, only prefix + metadata. 

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
    String sort = "label"; // String | Field to order by. This list holds tens of rows per account, so every column is offered and none needs an index.
    String order = "asc"; // String | Defaults to desc for the default field and asc for any other. Always tie-broken on id, so the order is total.
    try {
      ListApiKeys200Response result = apiInstance.listApiKeys(sort, order);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling ApiKeysApi#listApiKeys");
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
| **sort** | **String**| Field to order by. This list holds tens of rows per account, so every column is offered and none needs an index. | [optional] [default to created_at] [enum: label, created_at, last_used_at, expires_at] |
| **order** | **String**| Defaults to desc for the default field and asc for any other. Always tie-broken on id, so the order is total. | [optional] [enum: asc, desc] |

### Return type

[**ListApiKeys200Response**](ListApiKeys200Response.md)

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

<a id="revokeApiKey"></a>
# **revokeApiKey**
> revokeApiKey(id)

Revoke an API key

Soft-deletes (sets &#x60;revoked_at&#x60;) on the named key. The row stays for audit purposes; the key no longer authenticates.  You **cannot revoke the key currently being used** to make this call, that would lock you out. Use a different &#x60;tenant:admin&#x60; key. 

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
      apiInstance.revokeApiKey(id);
    } catch (ApiException e) {
      System.err.println("Exception when calling ApiKeysApi#revokeApiKey");
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
| **409** | Refused, key is the one in use for this request. |  -  |

<a id="rotateApiKey"></a>
# **rotateApiKey**
> CreateApiKey201Response rotateApiKey(id, rotateApiKeyRequest)

Rotate an API key

Issues a successor key and puts a short expiry on this one, so **both work until the overlap ends**. That window is the point: without it, rotation is revocation with extra steps and every caller has to swap credentials in the same instant.  The successor inherits this key&#39;s scopes, its label (the label names the integration, and the integration has not changed) and its test flag. Its full &#x60;secret&#x60; is in this response and nowhere else.  The response&#39;s &#x60;expires_at&#x60; is the **predecessor&#39;s** deadline, so you can see from the rotation itself how long you have to cut over.  A key that has already been rotated cannot be rotated again: chaining overlaps would leave several live keys for one integration, which is the opposite of the intent. Rotate the successor instead. 

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
    RotateApiKeyRequest rotateApiKeyRequest = new RotateApiKeyRequest(); // RotateApiKeyRequest | 
    try {
      CreateApiKey201Response result = apiInstance.rotateApiKey(id, rotateApiKeyRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling ApiKeysApi#rotateApiKey");
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
| **rotateApiKeyRequest** | [**RotateApiKeyRequest**](RotateApiKeyRequest.md)|  | [optional] |

### Return type

[**CreateApiKey201Response**](CreateApiKey201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The successor key. Its &#x60;secret&#x60; is shown only here; &#x60;expires_at&#x60; is the predecessor&#39;s deadline. |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |
| **409** | The key is revoked, or was already rotated. |  -  |

<a id="updateApiKey"></a>
# **updateApiKey**
> APIKey updateApiKey(id, updateApiKeyRequest)

Update an API key

Changes a key&#39;s label, scopes or expiry in place, without reissuing the secret.  **Every field is optional and absent means unchanged.** Renaming a key does not clear its expiry. For &#x60;expires_at&#x60; there are three distinct requests: omit the field to leave the expiry alone, send a timestamp to set one, and send an explicit &#x60;null&#x60; to remove one.  Scopes are replaced wholesale, not merged. This endpoint does not restrict which scopes you may grant, because &#x60;POST /v1/api-keys&#x60; never has either: a key with &#x60;tenant:admin&#x60; can already mint a key with any scope, so &#x60;tenant:admin&#x60; is root-equivalent for key management.  A revoked key cannot be updated. 

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
    UpdateApiKeyRequest updateApiKeyRequest = new UpdateApiKeyRequest(); // UpdateApiKeyRequest | 
    try {
      APIKey result = apiInstance.updateApiKey(id, updateApiKeyRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling ApiKeysApi#updateApiKey");
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
| **updateApiKeyRequest** | [**UpdateApiKeyRequest**](UpdateApiKeyRequest.md)|  | |

### Return type

[**APIKey**](APIKey.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated key. |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |
| **409** | The key is revoked and cannot be changed. |  -  |

