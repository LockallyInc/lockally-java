# TenantApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**getTenant**](TenantApi.md#getTenant) | **GET** /v1/tenant | Get the calling tenant |
| [**getTrackingPolicy**](TenantApi.md#getTrackingPolicy) | **GET** /v1/tracking | Get the engagement tracking policy |
| [**getUsage**](TenantApi.md#getUsage) | **GET** /v1/usage | Usage snapshot |
| [**updateTrackingPolicy**](TenantApi.md#updateTrackingPolicy) | **PUT** /v1/tracking | Update the engagement tracking policy |


<a id="getTenant"></a>
# **getTenant**
> Tenant getTenant()

Get the calling tenant

Returns the tenant the presented API key belongs to.

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.TenantApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    TenantApi apiInstance = new TenantApi(defaultClient);
    try {
      Tenant result = apiInstance.getTenant();
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling TenantApi#getTenant");
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

[**Tenant**](Tenant.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Tenant info |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

<a id="getTrackingPolicy"></a>
# **getTrackingPolicy**
> TrackingPolicy getTrackingPolicy()

Get the engagement tracking policy

Whether open and click tracking are enabled for this account. **Both are off until switched on**, and an account that has never set a policy reads as off rather than as an error.  &#x60;configured&#x60; reports whether this deployment holds a signing secret. Without one no tracking token can be minted or verified, so tracking cannot work however the flags are set, and a caller seeing &#x60;track_opens: true&#x60; with nothing arriving deserves to know why. 

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.TenantApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    TenantApi apiInstance = new TenantApi(defaultClient);
    try {
      TrackingPolicy result = apiInstance.getTrackingPolicy();
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling TenantApi#getTrackingPolicy");
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

[**TrackingPolicy**](TrackingPolicy.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The policy. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

<a id="getUsage"></a>
# **getUsage**
> GetUsage200Response getUsage()

Usage snapshot

Returns the tenant&#39;s current usage + cap consumption. Designed for poll-based alerting on the integrator side (e.g. \&quot;warn when daily quota is 80% used\&quot;). Computed live on request, so there is no cache, so callers should poll at most once per minute. 

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.TenantApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    TenantApi apiInstance = new TenantApi(defaultClient);
    try {
      GetUsage200Response result = apiInstance.getUsage();
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling TenantApi#getUsage");
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

[**GetUsage200Response**](GetUsage200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Usage snapshot |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

<a id="updateTrackingPolicy"></a>
# **updateTrackingPolicy**
> TrackingPolicy updateTrackingPolicy(updateTrackingPolicyRequest)

Update the engagement tracking policy

Enables or disables tracking for the account. Send either flag or both; an omitted flag is left unchanged rather than reset.  **Enabling this changes what Lockally collects about your recipients**, who have no relationship with us. You are the controller for them. What is collected is a user-agent string, a timestamp, and for a click the destination URL: **no IP address**, ever. The change is written to your audit log. 

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.TenantApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    TenantApi apiInstance = new TenantApi(defaultClient);
    UpdateTrackingPolicyRequest updateTrackingPolicyRequest = new UpdateTrackingPolicyRequest(); // UpdateTrackingPolicyRequest | 
    try {
      TrackingPolicy result = apiInstance.updateTrackingPolicy(updateTrackingPolicyRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling TenantApi#updateTrackingPolicy");
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
| **updateTrackingPolicyRequest** | [**UpdateTrackingPolicyRequest**](UpdateTrackingPolicyRequest.md)|  | |

### Return type

[**TrackingPolicy**](TrackingPolicy.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated policy. |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

