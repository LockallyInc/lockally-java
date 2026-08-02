# MailboxesApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**addSharedMember**](MailboxesApi.md#addSharedMember) | **POST** /v1/mailboxes/{email}/members | Add a shared mailbox member |
| [**listSharedMembers**](MailboxesApi.md#listSharedMembers) | **GET** /v1/mailboxes/{email}/members | List shared mailbox members |
| [**removeSharedMember**](MailboxesApi.md#removeSharedMember) | **DELETE** /v1/mailboxes/{email}/members/{memberEmail} | Remove a shared mailbox member |
| [**v1MailboxesEmailDelete**](MailboxesApi.md#v1MailboxesEmailDelete) | **DELETE** /v1/mailboxes/{email} | Soft-delete a mailbox |
| [**v1MailboxesEmailExportDownloadGet**](MailboxesApi.md#v1MailboxesEmailExportDownloadGet) | **GET** /v1/mailboxes/{email}/export/download | Download a previously-issued mailbox export |
| [**v1MailboxesEmailExportPost**](MailboxesApi.md#v1MailboxesEmailExportPost) | **POST** /v1/mailboxes/{email}/export | Request a mailbox export |
| [**v1MailboxesEmailGet**](MailboxesApi.md#v1MailboxesEmailGet) | **GET** /v1/mailboxes/{email} | Get a mailbox |
| [**v1MailboxesEmailPatch**](MailboxesApi.md#v1MailboxesEmailPatch) | **PATCH** /v1/mailboxes/{email} | Update a mailbox |
| [**v1MailboxesEmailVacationDelete**](MailboxesApi.md#v1MailboxesEmailVacationDelete) | **DELETE** /v1/mailboxes/{email}/vacation | Remove the vacation responder |
| [**v1MailboxesEmailVacationGet**](MailboxesApi.md#v1MailboxesEmailVacationGet) | **GET** /v1/mailboxes/{email}/vacation | Get the vacation responder |
| [**v1MailboxesEmailVacationPut**](MailboxesApi.md#v1MailboxesEmailVacationPut) | **PUT** /v1/mailboxes/{email}/vacation | Set the vacation responder |
| [**v1MailboxesGet**](MailboxesApi.md#v1MailboxesGet) | **GET** /v1/mailboxes | List mailboxes |
| [**v1MailboxesPost**](MailboxesApi.md#v1MailboxesPost) | **POST** /v1/mailboxes | Create a mailbox |
| [**v1VacationGet**](MailboxesApi.md#v1VacationGet) | **GET** /v1/vacation | List all vacation responders |


<a id="addSharedMember"></a>
# **addSharedMember**
> SharedMember addSharedMember(email, addSharedMemberRequest)

Add a shared mailbox member

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.MailboxesApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    MailboxesApi apiInstance = new MailboxesApi(defaultClient);
    String email = "email_example"; // String | 
    AddSharedMemberRequest addSharedMemberRequest = new AddSharedMemberRequest(); // AddSharedMemberRequest | 
    try {
      SharedMember result = apiInstance.addSharedMember(email, addSharedMemberRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling MailboxesApi#addSharedMember");
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
| **addSharedMemberRequest** | [**AddSharedMemberRequest**](AddSharedMemberRequest.md)|  | |

### Return type

[**SharedMember**](SharedMember.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Member added. |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |
| **409** | Already a member of this mailbox. |  -  |

<a id="listSharedMembers"></a>
# **listSharedMembers**
> ListSharedMembers200Response listSharedMembers(email)

List shared mailbox members

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.MailboxesApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    MailboxesApi apiInstance = new MailboxesApi(defaultClient);
    String email = "email_example"; // String | 
    try {
      ListSharedMembers200Response result = apiInstance.listSharedMembers(email);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling MailboxesApi#listSharedMembers");
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

[**ListSharedMembers200Response**](ListSharedMembers200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Members of the shared mailbox. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

<a id="removeSharedMember"></a>
# **removeSharedMember**
> removeSharedMember(email, memberEmail)

Remove a shared mailbox member

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.MailboxesApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    MailboxesApi apiInstance = new MailboxesApi(defaultClient);
    String email = "email_example"; // String | 
    String memberEmail = "memberEmail_example"; // String | 
    try {
      apiInstance.removeSharedMember(email, memberEmail);
    } catch (ApiException e) {
      System.err.println("Exception when calling MailboxesApi#removeSharedMember");
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
| **memberEmail** | **String**|  | |

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

<a id="v1MailboxesEmailDelete"></a>
# **v1MailboxesEmailDelete**
> v1MailboxesEmailDelete(email)

Soft-delete a mailbox

Sets &#x60;soft_deleted_at &#x3D; now()&#x60; and &#x60;hard_delete_after &#x3D; now() + 90d&#x60; per design D25. A background sweep (planned) will hard-delete after the window. The mailbox is also disabled immediately. 

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.MailboxesApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    MailboxesApi apiInstance = new MailboxesApi(defaultClient);
    String email = "email_example"; // String | 
    try {
      apiInstance.v1MailboxesEmailDelete(email);
    } catch (ApiException e) {
      System.err.println("Exception when calling MailboxesApi#v1MailboxesEmailDelete");
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

null (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | Soft-deleted. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

<a id="v1MailboxesEmailExportDownloadGet"></a>
# **v1MailboxesEmailExportDownloadGet**
> File v1MailboxesEmailExportDownloadGet(email, token)

Download a previously-issued mailbox export

Public endpoint (no Authorization header). Validates the one-shot token from the URL, marks it used, and streams an mbox file. Second GET with the same token returns 404 — tokens are single-use. 

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.MailboxesApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");

    MailboxesApi apiInstance = new MailboxesApi(defaultClient);
    String email = "email_example"; // String | 
    String token = "token_example"; // String | 
    try {
      File result = apiInstance.v1MailboxesEmailExportDownloadGet(email, token);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling MailboxesApi#v1MailboxesEmailExportDownloadGet");
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
| **token** | **String**|  | |

### Return type

[**File**](File.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/mbox, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | mbox stream. |  -  |
| **400** | Malformed request. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Token not found, already used, or expired. |  -  |

<a id="v1MailboxesEmailExportPost"></a>
# **v1MailboxesEmailExportPost**
> V1MailboxesEmailExportPost201Response v1MailboxesEmailExportPost(email)

Request a mailbox export

Issues a one-shot \&quot;presigned\&quot; download URL for the mailbox&#39;s content in mbox format. The URL works without an Authorization header — the token in the query string is the authz. TTL is 5 minutes; the token is consumed on first GET.  **v1 caveat:** the synthesized mbox only contains outbound mail (from &#x60;lockally.messages&#x60;). v2 swaps in Stalwart&#39;s export primitive for full inbox + folder structure + flags. The endpoint contract stays unchanged. 

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.MailboxesApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    MailboxesApi apiInstance = new MailboxesApi(defaultClient);
    String email = "email_example"; // String | 
    try {
      V1MailboxesEmailExportPost201Response result = apiInstance.v1MailboxesEmailExportPost(email);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling MailboxesApi#v1MailboxesEmailExportPost");
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

[**V1MailboxesEmailExportPost201Response**](V1MailboxesEmailExportPost201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Export token issued. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

<a id="v1MailboxesEmailGet"></a>
# **v1MailboxesEmailGet**
> Mailbox v1MailboxesEmailGet(email)

Get a mailbox

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.MailboxesApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    MailboxesApi apiInstance = new MailboxesApi(defaultClient);
    String email = "email_example"; // String | 
    try {
      Mailbox result = apiInstance.v1MailboxesEmailGet(email);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling MailboxesApi#v1MailboxesEmailGet");
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

[**Mailbox**](Mailbox.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Mailbox info. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

<a id="v1MailboxesEmailPatch"></a>
# **v1MailboxesEmailPatch**
> Mailbox v1MailboxesEmailPatch(email, v1MailboxesEmailPatchRequest)

Update a mailbox

Supply at least one of &#x60;password&#x60;, &#x60;quota_bytes&#x60;, &#x60;disabled&#x60;. Returns the updated mailbox. 

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.MailboxesApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    MailboxesApi apiInstance = new MailboxesApi(defaultClient);
    String email = "email_example"; // String | 
    V1MailboxesEmailPatchRequest v1MailboxesEmailPatchRequest = new V1MailboxesEmailPatchRequest(); // V1MailboxesEmailPatchRequest | 
    try {
      Mailbox result = apiInstance.v1MailboxesEmailPatch(email, v1MailboxesEmailPatchRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling MailboxesApi#v1MailboxesEmailPatch");
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
| **v1MailboxesEmailPatchRequest** | [**V1MailboxesEmailPatchRequest**](V1MailboxesEmailPatchRequest.md)|  | |

### Return type

[**Mailbox**](Mailbox.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Updated mailbox. |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

<a id="v1MailboxesEmailVacationDelete"></a>
# **v1MailboxesEmailVacationDelete**
> v1MailboxesEmailVacationDelete(email)

Remove the vacation responder

Idempotent — 204 whether or not a row existed.

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.MailboxesApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    MailboxesApi apiInstance = new MailboxesApi(defaultClient);
    String email = "email_example"; // String | 
    try {
      apiInstance.v1MailboxesEmailVacationDelete(email);
    } catch (ApiException e) {
      System.err.println("Exception when calling MailboxesApi#v1MailboxesEmailVacationDelete");
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

<a id="v1MailboxesEmailVacationGet"></a>
# **v1MailboxesEmailVacationGet**
> VacationResponder v1MailboxesEmailVacationGet(email)

Get the vacation responder

Returns the stored vacation rule or 404 if none is set.

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.MailboxesApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    MailboxesApi apiInstance = new MailboxesApi(defaultClient);
    String email = "email_example"; // String | 
    try {
      VacationResponder result = apiInstance.v1MailboxesEmailVacationGet(email);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling MailboxesApi#v1MailboxesEmailVacationGet");
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

[**VacationResponder**](VacationResponder.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Vacation responder. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

<a id="v1MailboxesEmailVacationPut"></a>
# **v1MailboxesEmailVacationPut**
> VacationResponder v1MailboxesEmailVacationPut(email, v1MailboxesEmailVacationPutRequest)

Set the vacation responder

Upsert — same endpoint creates or replaces the rule. Clears &#x60;synced_at&#x60;; the rule is staged on lockally until a sync worker pushes it to the mail server. 

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.MailboxesApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    MailboxesApi apiInstance = new MailboxesApi(defaultClient);
    String email = "email_example"; // String | 
    V1MailboxesEmailVacationPutRequest v1MailboxesEmailVacationPutRequest = new V1MailboxesEmailVacationPutRequest(); // V1MailboxesEmailVacationPutRequest | 
    try {
      VacationResponder result = apiInstance.v1MailboxesEmailVacationPut(email, v1MailboxesEmailVacationPutRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling MailboxesApi#v1MailboxesEmailVacationPut");
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
| **v1MailboxesEmailVacationPutRequest** | [**V1MailboxesEmailVacationPutRequest**](V1MailboxesEmailVacationPutRequest.md)|  | |

### Return type

[**VacationResponder**](VacationResponder.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Saved. |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

<a id="v1MailboxesGet"></a>
# **v1MailboxesGet**
> V1MailboxesGet200Response v1MailboxesGet(limit)

List mailboxes

Returns mailboxes under the calling tenant — active and soft-deleted. &#x60;?limit&#x3D;N&#x60; between 1 and 200 (default 50). 

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.MailboxesApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    MailboxesApi apiInstance = new MailboxesApi(defaultClient);
    Integer limit = 50; // Integer | 
    try {
      V1MailboxesGet200Response result = apiInstance.v1MailboxesGet(limit);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling MailboxesApi#v1MailboxesGet");
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
| **limit** | **Integer**|  | [optional] [default to 50] |

### Return type

[**V1MailboxesGet200Response**](V1MailboxesGet200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Mailbox list. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

<a id="v1MailboxesPost"></a>
# **v1MailboxesPost**
> Mailbox v1MailboxesPost(v1MailboxesPostRequest)

Create a mailbox

Creates a mailbox on a tenant-verified domain. If &#x60;password&#x60; is omitted, lockally generates a 16-char password and returns it in the response — shown once.  **Gate.** The mailbox&#39;s domain must already be registered AND verified for this tenant (via &#x60;/v1/domains&#x60; + &#x60;/v1/domains/{domain}/verify&#x60;).  **Idempotent.** Re-posting the same email returns the existing mailbox UNTOUCHED — password is NOT regenerated. To change a password, use PATCH instead. 

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.MailboxesApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    MailboxesApi apiInstance = new MailboxesApi(defaultClient);
    V1MailboxesPostRequest v1MailboxesPostRequest = new V1MailboxesPostRequest(); // V1MailboxesPostRequest | 
    try {
      Mailbox result = apiInstance.v1MailboxesPost(v1MailboxesPostRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling MailboxesApi#v1MailboxesPost");
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
| **v1MailboxesPostRequest** | [**V1MailboxesPostRequest**](V1MailboxesPostRequest.md)|  | |

### Return type

[**Mailbox**](Mailbox.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Mailbox already existed for this tenant (idempotent). |  -  |
| **201** | Mailbox created. &#x60;password&#x60; is in the response ONLY if generated. |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **409** | Email claimed by another tenant. |  -  |

<a id="v1VacationGet"></a>
# **v1VacationGet**
> V1VacationGet200Response v1VacationGet()

List all vacation responders

Returns every vacation responder for the calling tenant.

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.MailboxesApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    MailboxesApi apiInstance = new MailboxesApi(defaultClient);
    try {
      V1VacationGet200Response result = apiInstance.v1VacationGet();
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling MailboxesApi#v1VacationGet");
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

[**V1VacationGet200Response**](V1VacationGet200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

