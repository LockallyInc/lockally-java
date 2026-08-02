# DomainsApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**v1DomainsDomainDelete**](DomainsApi.md#v1DomainsDomainDelete) | **DELETE** /v1/domains/{domain} | Delete a domain |
| [**v1DomainsDomainGet**](DomainsApi.md#v1DomainsDomainGet) | **GET** /v1/domains/{domain} | Get a domain |
| [**v1DomainsDomainVerifyPost**](DomainsApi.md#v1DomainsDomainVerifyPost) | **POST** /v1/domains/{domain}/verify | Force-poll DNS verification |
| [**v1DomainsGet**](DomainsApi.md#v1DomainsGet) | **GET** /v1/domains | List domains |
| [**v1DomainsPost**](DomainsApi.md#v1DomainsPost) | **POST** /v1/domains | Register a domain |


<a id="v1DomainsDomainDelete"></a>
# **v1DomainsDomainDelete**
> v1DomainsDomainDelete(domain)

Delete a domain

Removes the domain registration. Refuses with 409 if any mailbox is still attached — delete the mailboxes first. 

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.DomainsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    DomainsApi apiInstance = new DomainsApi(defaultClient);
    String domain = "domain_example"; // String | 
    try {
      apiInstance.v1DomainsDomainDelete(domain);
    } catch (ApiException e) {
      System.err.println("Exception when calling DomainsApi#v1DomainsDomainDelete");
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
| **domain** | **String**|  | |

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
| **409** | Domain still has mailboxes attached. |  -  |

<a id="v1DomainsDomainGet"></a>
# **v1DomainsDomainGet**
> Domain v1DomainsDomainGet(domain)

Get a domain

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.DomainsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    DomainsApi apiInstance = new DomainsApi(defaultClient);
    String domain = "domain_example"; // String | 
    try {
      Domain result = apiInstance.v1DomainsDomainGet(domain);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling DomainsApi#v1DomainsDomainGet");
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
| **domain** | **String**|  | |

### Return type

[**Domain**](Domain.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Domain record including the DNS instructions to publish. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

<a id="v1DomainsDomainVerifyPost"></a>
# **v1DomainsDomainVerifyPost**
> Domain v1DomainsDomainVerifyPost(domain)

Force-poll DNS verification

Synchronously checks the &#x60;_lockally-verify.&lt;domain&gt;&#x60; TXT record against the stored verification token. Returns 200 either way: the returned &#x60;verified&#x60; boolean tells you whether DNS now confirms. Caller polls until &#x60;verified: true&#x60;. In v2 a background worker auto-polls and fires a &#x60;domain.verified&#x60; webhook. 

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.DomainsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    DomainsApi apiInstance = new DomainsApi(defaultClient);
    String domain = "domain_example"; // String | 
    try {
      Domain result = apiInstance.v1DomainsDomainVerifyPost(domain);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling DomainsApi#v1DomainsDomainVerifyPost");
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
| **domain** | **String**|  | |

### Return type

[**Domain**](Domain.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Current domain state (possibly newly verified). |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |
| **502** | Upstream DNS error (timeout, server unreachable). Retry. |  -  |

<a id="v1DomainsGet"></a>
# **v1DomainsGet**
> V1DomainsGet200Response v1DomainsGet()

List domains

Returns every domain registered under the calling tenant.

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.DomainsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    DomainsApi apiInstance = new DomainsApi(defaultClient);
    try {
      V1DomainsGet200Response result = apiInstance.v1DomainsGet();
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling DomainsApi#v1DomainsGet");
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

[**V1DomainsGet200Response**](V1DomainsGet200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Domain list |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

<a id="v1DomainsPost"></a>
# **v1DomainsPost**
> Domain v1DomainsPost(v1DomainsPostRequest)

Register a domain

Registers a new domain for the calling tenant. Generates a DKIM keypair and verification token. Returns DNS instructions the tenant must publish under their own DNS (verification TXT, SPF include, DKIM TXT, MX records to &#x60;mx1&#x60;/&#x60;mx2.lockally.com&#x60;, DMARC seed).  **Idempotent** — re-posting the same domain returns the existing record with the same DKIM keys and token (regenerating would break the tenant&#39;s published DNS). Returns 200 on idempotent hit, 201 on first create.  Returns 409 if the domain is already claimed by a different tenant. 

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.DomainsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    DomainsApi apiInstance = new DomainsApi(defaultClient);
    V1DomainsPostRequest v1DomainsPostRequest = new V1DomainsPostRequest(); // V1DomainsPostRequest | 
    try {
      Domain result = apiInstance.v1DomainsPost(v1DomainsPostRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling DomainsApi#v1DomainsPost");
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
| **v1DomainsPostRequest** | [**V1DomainsPostRequest**](V1DomainsPostRequest.md)|  | |

### Return type

[**Domain**](Domain.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Domain already registered to the calling tenant (idempotent). |  -  |
| **201** | Domain created. |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **409** | Domain claimed by another tenant. |  -  |

