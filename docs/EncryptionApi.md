# EncryptionApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**batchLookupPublicKeys**](EncryptionApi.md#batchLookupPublicKeys) | **GET** /v1/encryption/keys/lookup | Batch-lookup public keys by email |
| [**createEncryptionKey**](EncryptionApi.md#createEncryptionKey) | **POST** /v1/encryption/keys | Upload an encryption key pair |
| [**createEncryptionRecovery**](EncryptionApi.md#createEncryptionRecovery) | **POST** /v1/encryption/recovery | Store an encryption recovery blob |
| [**getEncryptionKey**](EncryptionApi.md#getEncryptionKey) | **GET** /v1/encryption/keys/{email} | Get encryption key for a mailbox |
| [**rotateEncryptionKey**](EncryptionApi.md#rotateEncryptionKey) | **POST** /v1/encryption/keys/rotate | Rotate an encryption key |


<a id="batchLookupPublicKeys"></a>
# **batchLookupPublicKeys**
> BatchLookupPublicKeys200Response batchLookupPublicKeys(emails)

Batch-lookup public keys by email

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.EncryptionApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    EncryptionApi apiInstance = new EncryptionApi(defaultClient);
    String emails = "emails_example"; // String | Comma-separated list of email addresses
    try {
      BatchLookupPublicKeys200Response result = apiInstance.batchLookupPublicKeys(emails);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling EncryptionApi#batchLookupPublicKeys");
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
| **emails** | **String**| Comma-separated list of email addresses | |

### Return type

[**BatchLookupPublicKeys200Response**](BatchLookupPublicKeys200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Public keys for requested emails |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

<a id="createEncryptionKey"></a>
# **createEncryptionKey**
> CreateEncryptionKey201Response createEncryptionKey(createEncryptionKeyRequest)

Upload an encryption key pair

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.EncryptionApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    EncryptionApi apiInstance = new EncryptionApi(defaultClient);
    CreateEncryptionKeyRequest createEncryptionKeyRequest = new CreateEncryptionKeyRequest(); // CreateEncryptionKeyRequest | 
    try {
      CreateEncryptionKey201Response result = apiInstance.createEncryptionKey(createEncryptionKeyRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling EncryptionApi#createEncryptionKey");
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
| **createEncryptionKeyRequest** | [**CreateEncryptionKeyRequest**](CreateEncryptionKeyRequest.md)|  | |

### Return type

[**CreateEncryptionKey201Response**](CreateEncryptionKey201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Key pair stored |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

<a id="createEncryptionRecovery"></a>
# **createEncryptionRecovery**
> createEncryptionRecovery(createEncryptionRecoveryRequest)

Store an encryption recovery blob

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.EncryptionApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    EncryptionApi apiInstance = new EncryptionApi(defaultClient);
    CreateEncryptionRecoveryRequest createEncryptionRecoveryRequest = new CreateEncryptionRecoveryRequest(); // CreateEncryptionRecoveryRequest | 
    try {
      apiInstance.createEncryptionRecovery(createEncryptionRecoveryRequest);
    } catch (ApiException e) {
      System.err.println("Exception when calling EncryptionApi#createEncryptionRecovery");
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
| **createEncryptionRecoveryRequest** | [**CreateEncryptionRecoveryRequest**](CreateEncryptionRecoveryRequest.md)|  | |

### Return type

null (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | Recovery blob stored |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

<a id="getEncryptionKey"></a>
# **getEncryptionKey**
> GetEncryptionKey200Response getEncryptionKey(email)

Get encryption key for a mailbox

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.EncryptionApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    EncryptionApi apiInstance = new EncryptionApi(defaultClient);
    String email = "email_example"; // String | 
    try {
      GetEncryptionKey200Response result = apiInstance.getEncryptionKey(email);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling EncryptionApi#getEncryptionKey");
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

[**GetEncryptionKey200Response**](GetEncryptionKey200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Encryption key details |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

<a id="rotateEncryptionKey"></a>
# **rotateEncryptionKey**
> rotateEncryptionKey(rotateEncryptionKeyRequest)

Rotate an encryption key

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.EncryptionApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    EncryptionApi apiInstance = new EncryptionApi(defaultClient);
    RotateEncryptionKeyRequest rotateEncryptionKeyRequest = new RotateEncryptionKeyRequest(); // RotateEncryptionKeyRequest | 
    try {
      apiInstance.rotateEncryptionKey(rotateEncryptionKeyRequest);
    } catch (ApiException e) {
      System.err.println("Exception when calling EncryptionApi#rotateEncryptionKey");
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
| **rotateEncryptionKeyRequest** | [**RotateEncryptionKeyRequest**](RotateEncryptionKeyRequest.md)|  | |

### Return type

null (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | Key rotated |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

