# MailboxesApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**addSharedMember**](MailboxesApi.md#addSharedMember) | **POST** /v1/mailboxes/{email}/members | Add a shared mailbox member |
| [**createMailbox**](MailboxesApi.md#createMailbox) | **POST** /v1/mailboxes | Create a mailbox |
| [**deleteMailbox**](MailboxesApi.md#deleteMailbox) | **DELETE** /v1/mailboxes/{email} | Soft-delete a mailbox |
| [**deleteVacationResponder**](MailboxesApi.md#deleteVacationResponder) | **DELETE** /v1/mailboxes/{email}/vacation | Remove the vacation responder |
| [**downloadMailboxExport**](MailboxesApi.md#downloadMailboxExport) | **GET** /v1/mailboxes/{email}/export/download | Download a previously-issued mailbox export |
| [**exportMailbox**](MailboxesApi.md#exportMailbox) | **POST** /v1/mailboxes/{email}/export | Request a mailbox export |
| [**getMailbox**](MailboxesApi.md#getMailbox) | **GET** /v1/mailboxes/{email} | Get a mailbox |
| [**getVacationResponder**](MailboxesApi.md#getVacationResponder) | **GET** /v1/mailboxes/{email}/vacation | Get the vacation responder |
| [**listMailboxes**](MailboxesApi.md#listMailboxes) | **GET** /v1/mailboxes | List mailboxes |
| [**listSharedMembers**](MailboxesApi.md#listSharedMembers) | **GET** /v1/mailboxes/{email}/members | List shared mailbox members |
| [**listVacationResponders**](MailboxesApi.md#listVacationResponders) | **GET** /v1/vacation | List all vacation responders |
| [**removeSharedMember**](MailboxesApi.md#removeSharedMember) | **DELETE** /v1/mailboxes/{email}/members/{memberEmail} | Remove a shared mailbox member |
| [**setVacationResponder**](MailboxesApi.md#setVacationResponder) | **PUT** /v1/mailboxes/{email}/vacation | Set the vacation responder |
| [**updateMailbox**](MailboxesApi.md#updateMailbox) | **PATCH** /v1/mailboxes/{email} | Update a mailbox |


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

<a id="createMailbox"></a>
# **createMailbox**
> Mailbox createMailbox(createMailboxRequest)

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
    CreateMailboxRequest createMailboxRequest = new CreateMailboxRequest(); // CreateMailboxRequest | 
    try {
      Mailbox result = apiInstance.createMailbox(createMailboxRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling MailboxesApi#createMailbox");
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
| **createMailboxRequest** | [**CreateMailboxRequest**](CreateMailboxRequest.md)|  | |

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

<a id="deleteMailbox"></a>
# **deleteMailbox**
> deleteMailbox(email)

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
      apiInstance.deleteMailbox(email);
    } catch (ApiException e) {
      System.err.println("Exception when calling MailboxesApi#deleteMailbox");
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

<a id="deleteVacationResponder"></a>
# **deleteVacationResponder**
> deleteVacationResponder(email)

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
      apiInstance.deleteVacationResponder(email);
    } catch (ApiException e) {
      System.err.println("Exception when calling MailboxesApi#deleteVacationResponder");
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

<a id="downloadMailboxExport"></a>
# **downloadMailboxExport**
> File downloadMailboxExport(email, token)

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
      File result = apiInstance.downloadMailboxExport(email, token);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling MailboxesApi#downloadMailboxExport");
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

<a id="exportMailbox"></a>
# **exportMailbox**
> ExportMailbox201Response exportMailbox(email)

Request a mailbox export

Issues a one-shot \&quot;presigned\&quot; download URL for the mailbox&#39;s content in mbox format. The URL works without an Authorization header — the token in the query string is the authz. TTL is 5 minutes; the token is consumed on first GET.  **v1 caveat:** the synthesized mbox only contains outbound mail (from &#x60;lockally.messages&#x60;). v2 swaps in Stalwart&#39;s export primitive for full inbox + folder structure + flags. The endpoint contract stays unchanged.  **Scope changed:** this used to accept &#x60;mailboxes:read&#x60;. It takes any mailbox in the tenant and returns that mailbox&#39;s mail, so it now requires &#x60;tenant:admin&#x60;, matching &#x60;POST /v1/ediscovery/export&#x60;. A key scoped &#x60;mailboxes:read&#x60; gets 403 and has to be reissued; admin console sessions are unaffected. 

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
      ExportMailbox201Response result = apiInstance.exportMailbox(email);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling MailboxesApi#exportMailbox");
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

[**ExportMailbox201Response**](ExportMailbox201Response.md)

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

<a id="getMailbox"></a>
# **getMailbox**
> Mailbox getMailbox(email)

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
      Mailbox result = apiInstance.getMailbox(email);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling MailboxesApi#getMailbox");
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

<a id="getVacationResponder"></a>
# **getVacationResponder**
> VacationResponder getVacationResponder(email)

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
      VacationResponder result = apiInstance.getVacationResponder(email);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling MailboxesApi#getVacationResponder");
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

<a id="listMailboxes"></a>
# **listMailboxes**
> ListMailboxes200Response listMailboxes(limit)

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
      ListMailboxes200Response result = apiInstance.listMailboxes(limit);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling MailboxesApi#listMailboxes");
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

[**ListMailboxes200Response**](ListMailboxes200Response.md)

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

<a id="listVacationResponders"></a>
# **listVacationResponders**
> ListVacationResponders200Response listVacationResponders()

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
      ListVacationResponders200Response result = apiInstance.listVacationResponders();
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling MailboxesApi#listVacationResponders");
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

[**ListVacationResponders200Response**](ListVacationResponders200Response.md)

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

<a id="setVacationResponder"></a>
# **setVacationResponder**
> VacationResponder setVacationResponder(email, setVacationResponderRequest)

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
    SetVacationResponderRequest setVacationResponderRequest = new SetVacationResponderRequest(); // SetVacationResponderRequest | 
    try {
      VacationResponder result = apiInstance.setVacationResponder(email, setVacationResponderRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling MailboxesApi#setVacationResponder");
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
| **setVacationResponderRequest** | [**SetVacationResponderRequest**](SetVacationResponderRequest.md)|  | |

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

<a id="updateMailbox"></a>
# **updateMailbox**
> Mailbox updateMailbox(email, updateMailboxRequest)

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
    UpdateMailboxRequest updateMailboxRequest = new UpdateMailboxRequest(); // UpdateMailboxRequest | 
    try {
      Mailbox result = apiInstance.updateMailbox(email, updateMailboxRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling MailboxesApi#updateMailbox");
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
| **updateMailboxRequest** | [**UpdateMailboxRequest**](UpdateMailboxRequest.md)|  | |

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

