# AdminsApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**deleteAdmin**](AdminsApi.md#deleteAdmin) | **DELETE** /v1/admins/{id} | Delete an admin |
| [**inviteAdmin**](AdminsApi.md#inviteAdmin) | **POST** /v1/admins | Invite a new admin |
| [**listAdmins**](AdminsApi.md#listAdmins) | **GET** /v1/admins | List tenant admins |
| [**updateAdmin**](AdminsApi.md#updateAdmin) | **PATCH** /v1/admins/{id} | Update an admin |


<a id="deleteAdmin"></a>
# **deleteAdmin**
> deleteAdmin(id)

Delete an admin

Hard-delete. Cascade-drops the admin&#39;s sessions (immediate revocation). Same safety rails as PATCH disabled&#x3D;true. 

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.AdminsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    AdminsApi apiInstance = new AdminsApi(defaultClient);
    UUID id = UUID.randomUUID(); // UUID | 
    try {
      apiInstance.deleteAdmin(id);
    } catch (ApiException e) {
      System.err.println("Exception when calling AdminsApi#deleteAdmin");
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
| **204** | Deleted. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |
| **409** | Self-delete on session bearer, or last-admin safeguard. |  -  |

<a id="inviteAdmin"></a>
# **inviteAdmin**
> AdminFull inviteAdmin(inviteAdminRequest)

Invite a new admin

Creates a new tenant admin. If &#x60;password&#x60; is omitted, lockally generates a 16-char password and returns it ONCE in the response. Email is case-insensitive and unique per tenant. 

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.AdminsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    AdminsApi apiInstance = new AdminsApi(defaultClient);
    InviteAdminRequest inviteAdminRequest = new InviteAdminRequest(); // InviteAdminRequest | 
    try {
      AdminFull result = apiInstance.inviteAdmin(inviteAdminRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling AdminsApi#inviteAdmin");
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
| **inviteAdminRequest** | [**InviteAdminRequest**](InviteAdminRequest.md)|  | |

### Return type

[**AdminFull**](AdminFull.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Created. &#x60;password&#x60; populated ONLY if generated. |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **409** | Email already an admin on this tenant. |  -  |

<a id="listAdmins"></a>
# **listAdmins**
> ListAdmins200Response listAdmins()

List tenant admins

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.AdminsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    AdminsApi apiInstance = new AdminsApi(defaultClient);
    try {
      ListAdmins200Response result = apiInstance.listAdmins();
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling AdminsApi#listAdmins");
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

[**ListAdmins200Response**](ListAdmins200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Admin list. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

<a id="updateAdmin"></a>
# **updateAdmin**
> AdminFull updateAdmin(id, updateAdminRequest)

Update an admin

Supply at least one of &#x60;password&#x60;, &#x60;display_name&#x60;, &#x60;role&#x60;, &#x60;disabled&#x60;.  **Safety rails.** A session bearer (adm_sess_*) cannot disable itself, use another admin or an API key (which bypasses the self-rail). Disabling the last active admin returns 409 to prevent orphaning the tenant from its console. 

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.AdminsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    AdminsApi apiInstance = new AdminsApi(defaultClient);
    UUID id = UUID.randomUUID(); // UUID | 
    UpdateAdminRequest updateAdminRequest = new UpdateAdminRequest(); // UpdateAdminRequest | 
    try {
      AdminFull result = apiInstance.updateAdmin(id, updateAdminRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling AdminsApi#updateAdmin");
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
| **updateAdminRequest** | [**UpdateAdminRequest**](UpdateAdminRequest.md)|  | |

### Return type

[**AdminFull**](AdminFull.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Updated admin. |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |
| **409** | Self-disable on session bearer, or last-admin safeguard. |  -  |

