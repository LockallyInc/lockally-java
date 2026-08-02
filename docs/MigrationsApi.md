# MigrationsApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**cancelMigration**](MigrationsApi.md#cancelMigration) | **POST** /v1/migrations/{id}/cancel | Cancel a running migration |
| [**checkMigrationDNS**](MigrationsApi.md#checkMigrationDNS) | **GET** /v1/migrations/{id}/dns-check | Check DNS readiness for cutover |
| [**createMigration**](MigrationsApi.md#createMigration) | **POST** /v1/migrations | Create a migration |
| [**createMigrationCredential**](MigrationsApi.md#createMigrationCredential) | **POST** /v1/migrations/credentials | Store a migration credential |
| [**deleteMigration**](MigrationsApi.md#deleteMigration) | **DELETE** /v1/migrations/{id} | Delete a migration |
| [**deleteMigrationCredential**](MigrationsApi.md#deleteMigrationCredential) | **DELETE** /v1/migrations/credentials/{id} | Delete a migration credential |
| [**deltaSyncMigration**](MigrationsApi.md#deltaSyncMigration) | **POST** /v1/migrations/{id}/delta-sync | Run a delta sync |
| [**discoverMigration**](MigrationsApi.md#discoverMigration) | **POST** /v1/migrations/{id}/discover | Discover source mailboxes |
| [**finalSyncMigration**](MigrationsApi.md#finalSyncMigration) | **POST** /v1/migrations/{id}/final-sync | Run the final sync before cutover |
| [**getMigration**](MigrationsApi.md#getMigration) | **GET** /v1/migrations/{id} | Get a migration |
| [**getMigrationProgress**](MigrationsApi.md#getMigrationProgress) | **GET** /v1/migrations/{id}/progress | Get migration progress |
| [**listMigrationCredentials**](MigrationsApi.md#listMigrationCredentials) | **GET** /v1/migrations/credentials | List migration credentials |
| [**listMigrationEvents**](MigrationsApi.md#listMigrationEvents) | **GET** /v1/migrations/{id}/events | List migration events |
| [**listMigrationMailboxes**](MigrationsApi.md#listMigrationMailboxes) | **GET** /v1/migrations/{id}/mailboxes | List migration mailboxes |
| [**listMigrations**](MigrationsApi.md#listMigrations) | **GET** /v1/migrations | List migrations |
| [**mapMigration**](MigrationsApi.md#mapMigration) | **POST** /v1/migrations/{id}/map | Map source to destination mailboxes |
| [**retryMigration**](MigrationsApi.md#retryMigration) | **POST** /v1/migrations/{id}/retry | Retry a failed or cancelled migration |
| [**startMigration**](MigrationsApi.md#startMigration) | **POST** /v1/migrations/{id}/start | Start the migration |
| [**updateMigration**](MigrationsApi.md#updateMigration) | **PATCH** /v1/migrations/{id} | Update a migration |
| [**updateMigrationMailbox**](MigrationsApi.md#updateMigrationMailbox) | **PATCH** /v1/migrations/{id}/mailboxes/{mbxId} | Update a migration mailbox |
| [**validateMigration**](MigrationsApi.md#validateMigration) | **POST** /v1/migrations/{id}/validate | Validate migrated data |


<a id="cancelMigration"></a>
# **cancelMigration**
> DiscoverMigration202Response cancelMigration(id)

Cancel a running migration

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.MigrationsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    MigrationsApi apiInstance = new MigrationsApi(defaultClient);
    UUID id = UUID.randomUUID(); // UUID | 
    try {
      DiscoverMigration202Response result = apiInstance.cancelMigration(id);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling MigrationsApi#cancelMigration");
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

[**DiscoverMigration202Response**](DiscoverMigration202Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Migration cancelled |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |
| **409** | Cannot cancel migration from its current status. |  -  |
| **503** | Service is temporarily unable to handle the request (e.g. database unreachable). |  -  |

<a id="checkMigrationDNS"></a>
# **checkMigrationDNS**
> Object checkMigrationDNS(id)

Check DNS readiness for cutover

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.MigrationsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    MigrationsApi apiInstance = new MigrationsApi(defaultClient);
    UUID id = UUID.randomUUID(); // UUID | 
    try {
      Object result = apiInstance.checkMigrationDNS(id);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling MigrationsApi#checkMigrationDNS");
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

**Object**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | DNS readiness check results |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |
| **503** | Service is temporarily unable to handle the request (e.g. database unreachable). |  -  |

<a id="createMigration"></a>
# **createMigration**
> Migration createMigration(createMigrationRequest)

Create a migration

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.MigrationsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    MigrationsApi apiInstance = new MigrationsApi(defaultClient);
    CreateMigrationRequest createMigrationRequest = new CreateMigrationRequest(); // CreateMigrationRequest | 
    try {
      Migration result = apiInstance.createMigration(createMigrationRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling MigrationsApi#createMigration");
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
| **createMigrationRequest** | [**CreateMigrationRequest**](CreateMigrationRequest.md)|  | |

### Return type

[**Migration**](Migration.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Migration created |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **503** | Service is temporarily unable to handle the request (e.g. database unreachable). |  -  |

<a id="createMigrationCredential"></a>
# **createMigrationCredential**
> MigrationCredential createMigrationCredential(createMigrationCredentialRequest)

Store a migration credential

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.MigrationsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    MigrationsApi apiInstance = new MigrationsApi(defaultClient);
    CreateMigrationCredentialRequest createMigrationCredentialRequest = new CreateMigrationCredentialRequest(); // CreateMigrationCredentialRequest | 
    try {
      MigrationCredential result = apiInstance.createMigrationCredential(createMigrationCredentialRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling MigrationsApi#createMigrationCredential");
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
| **createMigrationCredentialRequest** | [**CreateMigrationCredentialRequest**](CreateMigrationCredentialRequest.md)|  | |

### Return type

[**MigrationCredential**](MigrationCredential.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Credential stored |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **503** | Service is temporarily unable to handle the request (e.g. database unreachable). |  -  |

<a id="deleteMigration"></a>
# **deleteMigration**
> deleteMigration(id)

Delete a migration

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.MigrationsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    MigrationsApi apiInstance = new MigrationsApi(defaultClient);
    UUID id = UUID.randomUUID(); // UUID | 
    try {
      apiInstance.deleteMigration(id);
    } catch (ApiException e) {
      System.err.println("Exception when calling MigrationsApi#deleteMigration");
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
| **204** | Migration deleted |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |
| **409** | Can only delete migrations in draft, completed, failed, or cancelled status. |  -  |
| **503** | Service is temporarily unable to handle the request (e.g. database unreachable). |  -  |

<a id="deleteMigrationCredential"></a>
# **deleteMigrationCredential**
> deleteMigrationCredential(id)

Delete a migration credential

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.MigrationsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    MigrationsApi apiInstance = new MigrationsApi(defaultClient);
    UUID id = UUID.randomUUID(); // UUID | 
    try {
      apiInstance.deleteMigrationCredential(id);
    } catch (ApiException e) {
      System.err.println("Exception when calling MigrationsApi#deleteMigrationCredential");
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
| **204** | Credential deleted |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |
| **503** | Service is temporarily unable to handle the request (e.g. database unreachable). |  -  |

<a id="deltaSyncMigration"></a>
# **deltaSyncMigration**
> StartMigration202Response deltaSyncMigration(id)

Run a delta sync

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.MigrationsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    MigrationsApi apiInstance = new MigrationsApi(defaultClient);
    UUID id = UUID.randomUUID(); // UUID | 
    try {
      StartMigration202Response result = apiInstance.deltaSyncMigration(id);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling MigrationsApi#deltaSyncMigration");
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

[**StartMigration202Response**](StartMigration202Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **202** | Delta sync started |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |
| **409** | Migration is not in staged status. |  -  |
| **503** | Service is temporarily unable to handle the request (e.g. database unreachable). |  -  |

<a id="discoverMigration"></a>
# **discoverMigration**
> DiscoverMigration202Response discoverMigration(id)

Discover source mailboxes

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.MigrationsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    MigrationsApi apiInstance = new MigrationsApi(defaultClient);
    UUID id = UUID.randomUUID(); // UUID | 
    try {
      DiscoverMigration202Response result = apiInstance.discoverMigration(id);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling MigrationsApi#discoverMigration");
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

[**DiscoverMigration202Response**](DiscoverMigration202Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **202** | Discovery started |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |
| **409** | Migration is not in draft status. |  -  |
| **503** | Service is temporarily unable to handle the request (e.g. database unreachable). |  -  |

<a id="finalSyncMigration"></a>
# **finalSyncMigration**
> StartMigration202Response finalSyncMigration(id)

Run the final sync before cutover

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.MigrationsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    MigrationsApi apiInstance = new MigrationsApi(defaultClient);
    UUID id = UUID.randomUUID(); // UUID | 
    try {
      StartMigration202Response result = apiInstance.finalSyncMigration(id);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling MigrationsApi#finalSyncMigration");
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

[**StartMigration202Response**](StartMigration202Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **202** | Final sync started |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |
| **409** | Migration is not in cutover_pending status. |  -  |
| **503** | Service is temporarily unable to handle the request (e.g. database unreachable). |  -  |

<a id="getMigration"></a>
# **getMigration**
> Migration getMigration(id)

Get a migration

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.MigrationsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    MigrationsApi apiInstance = new MigrationsApi(defaultClient);
    UUID id = UUID.randomUUID(); // UUID | 
    try {
      Migration result = apiInstance.getMigration(id);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling MigrationsApi#getMigration");
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

[**Migration**](Migration.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Migration details |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |
| **503** | Service is temporarily unable to handle the request (e.g. database unreachable). |  -  |

<a id="getMigrationProgress"></a>
# **getMigrationProgress**
> MigrationProgress getMigrationProgress(id)

Get migration progress

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.MigrationsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    MigrationsApi apiInstance = new MigrationsApi(defaultClient);
    UUID id = UUID.randomUUID(); // UUID | 
    try {
      MigrationProgress result = apiInstance.getMigrationProgress(id);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling MigrationsApi#getMigrationProgress");
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

[**MigrationProgress**](MigrationProgress.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Migration progress |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |
| **503** | Service is temporarily unable to handle the request (e.g. database unreachable). |  -  |

<a id="listMigrationCredentials"></a>
# **listMigrationCredentials**
> ListMigrationCredentials200Response listMigrationCredentials()

List migration credentials

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.MigrationsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    MigrationsApi apiInstance = new MigrationsApi(defaultClient);
    try {
      ListMigrationCredentials200Response result = apiInstance.listMigrationCredentials();
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling MigrationsApi#listMigrationCredentials");
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

[**ListMigrationCredentials200Response**](ListMigrationCredentials200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Credential list |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **503** | Service is temporarily unable to handle the request (e.g. database unreachable). |  -  |

<a id="listMigrationEvents"></a>
# **listMigrationEvents**
> ListMigrationEvents200Response listMigrationEvents(id)

List migration events

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.MigrationsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    MigrationsApi apiInstance = new MigrationsApi(defaultClient);
    UUID id = UUID.randomUUID(); // UUID | 
    try {
      ListMigrationEvents200Response result = apiInstance.listMigrationEvents(id);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling MigrationsApi#listMigrationEvents");
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

[**ListMigrationEvents200Response**](ListMigrationEvents200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Migration event list |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |
| **503** | Service is temporarily unable to handle the request (e.g. database unreachable). |  -  |

<a id="listMigrationMailboxes"></a>
# **listMigrationMailboxes**
> ListMigrationMailboxes200Response listMigrationMailboxes(id)

List migration mailboxes

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.MigrationsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    MigrationsApi apiInstance = new MigrationsApi(defaultClient);
    UUID id = UUID.randomUUID(); // UUID | 
    try {
      ListMigrationMailboxes200Response result = apiInstance.listMigrationMailboxes(id);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling MigrationsApi#listMigrationMailboxes");
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

[**ListMigrationMailboxes200Response**](ListMigrationMailboxes200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Migration mailbox list |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |
| **503** | Service is temporarily unable to handle the request (e.g. database unreachable). |  -  |

<a id="listMigrations"></a>
# **listMigrations**
> ListMigrations200Response listMigrations()

List migrations

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.MigrationsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    MigrationsApi apiInstance = new MigrationsApi(defaultClient);
    try {
      ListMigrations200Response result = apiInstance.listMigrations();
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling MigrationsApi#listMigrations");
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

[**ListMigrations200Response**](ListMigrations200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Migration list |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **503** | Service is temporarily unable to handle the request (e.g. database unreachable). |  -  |

<a id="mapMigration"></a>
# **mapMigration**
> DiscoverMigration202Response mapMigration(id, mapMigrationRequest)

Map source to destination mailboxes

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.MigrationsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    MigrationsApi apiInstance = new MigrationsApi(defaultClient);
    UUID id = UUID.randomUUID(); // UUID | 
    MapMigrationRequest mapMigrationRequest = new MapMigrationRequest(); // MapMigrationRequest | 
    try {
      DiscoverMigration202Response result = apiInstance.mapMigration(id, mapMigrationRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling MigrationsApi#mapMigration");
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
| **mapMigrationRequest** | [**MapMigrationRequest**](MapMigrationRequest.md)|  | |

### Return type

[**DiscoverMigration202Response**](DiscoverMigration202Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Mappings applied |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |
| **503** | Service is temporarily unable to handle the request (e.g. database unreachable). |  -  |

<a id="retryMigration"></a>
# **retryMigration**
> DiscoverMigration202Response retryMigration(id)

Retry a failed or cancelled migration

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.MigrationsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    MigrationsApi apiInstance = new MigrationsApi(defaultClient);
    UUID id = UUID.randomUUID(); // UUID | 
    try {
      DiscoverMigration202Response result = apiInstance.retryMigration(id);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling MigrationsApi#retryMigration");
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

[**DiscoverMigration202Response**](DiscoverMigration202Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Migration retried |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |
| **409** | Migration is not in failed or cancelled status. |  -  |
| **503** | Service is temporarily unable to handle the request (e.g. database unreachable). |  -  |

<a id="startMigration"></a>
# **startMigration**
> StartMigration202Response startMigration(id)

Start the migration

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.MigrationsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    MigrationsApi apiInstance = new MigrationsApi(defaultClient);
    UUID id = UUID.randomUUID(); // UUID | 
    try {
      StartMigration202Response result = apiInstance.startMigration(id);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling MigrationsApi#startMigration");
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

[**StartMigration202Response**](StartMigration202Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **202** | Migration started |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |
| **409** | Migration is not in mapped or pilot_complete status. |  -  |
| **503** | Service is temporarily unable to handle the request (e.g. database unreachable). |  -  |

<a id="updateMigration"></a>
# **updateMigration**
> Migration updateMigration(id, updateMigrationRequest)

Update a migration

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.MigrationsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    MigrationsApi apiInstance = new MigrationsApi(defaultClient);
    UUID id = UUID.randomUUID(); // UUID | 
    UpdateMigrationRequest updateMigrationRequest = new UpdateMigrationRequest(); // UpdateMigrationRequest | 
    try {
      Migration result = apiInstance.updateMigration(id, updateMigrationRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling MigrationsApi#updateMigration");
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
| **updateMigrationRequest** | [**UpdateMigrationRequest**](UpdateMigrationRequest.md)|  | |

### Return type

[**Migration**](Migration.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Migration updated |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |
| **503** | Service is temporarily unable to handle the request (e.g. database unreachable). |  -  |

<a id="updateMigrationMailbox"></a>
# **updateMigrationMailbox**
> updateMigrationMailbox(id, mbxId, updateMigrationMailboxRequest)

Update a migration mailbox

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.MigrationsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    MigrationsApi apiInstance = new MigrationsApi(defaultClient);
    UUID id = UUID.randomUUID(); // UUID | 
    UUID mbxId = UUID.randomUUID(); // UUID | 
    UpdateMigrationMailboxRequest updateMigrationMailboxRequest = new UpdateMigrationMailboxRequest(); // UpdateMigrationMailboxRequest | 
    try {
      apiInstance.updateMigrationMailbox(id, mbxId, updateMigrationMailboxRequest);
    } catch (ApiException e) {
      System.err.println("Exception when calling MigrationsApi#updateMigrationMailbox");
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
| **mbxId** | **UUID**|  | |
| **updateMigrationMailboxRequest** | [**UpdateMigrationMailboxRequest**](UpdateMigrationMailboxRequest.md)|  | |

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
| **204** | Mailbox updated |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |
| **503** | Service is temporarily unable to handle the request (e.g. database unreachable). |  -  |

<a id="validateMigration"></a>
# **validateMigration**
> StartMigration202Response validateMigration(id)

Validate migrated data

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.MigrationsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    MigrationsApi apiInstance = new MigrationsApi(defaultClient);
    UUID id = UUID.randomUUID(); // UUID | 
    try {
      StartMigration202Response result = apiInstance.validateMigration(id);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling MigrationsApi#validateMigration");
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

[**StartMigration202Response**](StartMigration202Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **202** | Validation started |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |
| **409** | Migration is not in final_syncing status. |  -  |
| **503** | Service is temporarily unable to handle the request (e.g. database unreachable). |  -  |

