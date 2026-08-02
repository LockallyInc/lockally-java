# AgentsApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**v1ApiKeysKeyIDMailboxesGet**](AgentsApi.md#v1ApiKeysKeyIDMailboxesGet) | **GET** /v1/api-keys/{keyID}/mailboxes | List a key&#39;s mailbox grants |
| [**v1ApiKeysKeyIDMailboxesMailboxIDDelete**](AgentsApi.md#v1ApiKeysKeyIDMailboxesMailboxIDDelete) | **DELETE** /v1/api-keys/{keyID}/mailboxes/{mailboxID} | Revoke a mailbox grant |
| [**v1ApiKeysKeyIDMailboxesPost**](AgentsApi.md#v1ApiKeysKeyIDMailboxesPost) | **POST** /v1/api-keys/{keyID}/mailboxes | Grant a mailbox to a key |
| [**v1AuthWhoamiGet**](AgentsApi.md#v1AuthWhoamiGet) | **GET** /v1/auth/whoami | Introspect the calling credentials |
| [**v1ContactsLookupGet**](AgentsApi.md#v1ContactsLookupGet) | **GET** /v1/contacts/lookup | Who is this sender? |
| [**v1InboxesGet**](AgentsApi.md#v1InboxesGet) | **GET** /v1/inboxes | List granted inboxes |
| [**v1InboxesMailboxMessagesPost**](AgentsApi.md#v1InboxesMailboxMessagesPost) | **POST** /v1/inboxes/{mailbox}/messages | Start a new conversation (agent stream) |
| [**v1InboxesMailboxThreadsGet**](AgentsApi.md#v1InboxesMailboxThreadsGet) | **GET** /v1/inboxes/{mailbox}/threads | List conversation threads |
| [**v1ThreadsThreadIDGet**](AgentsApi.md#v1ThreadsThreadIDGet) | **GET** /v1/threads/{threadID} | Get a whole conversation |
| [**v1ThreadsThreadIDMessagesMessageIDAttachmentsIdxGet**](AgentsApi.md#v1ThreadsThreadIDMessagesMessageIDAttachmentsIdxGet) | **GET** /v1/threads/{threadID}/messages/{messageID}/attachments/{idx} | Download an attachment |
| [**v1ThreadsThreadIDMessagesMessageIDGet**](AgentsApi.md#v1ThreadsThreadIDMessagesMessageIDGet) | **GET** /v1/threads/{threadID}/messages/{messageID} | Get one message with body |
| [**v1ThreadsThreadIDMessagesMessageIDReadPost**](AgentsApi.md#v1ThreadsThreadIDMessagesMessageIDReadPost) | **POST** /v1/threads/{threadID}/messages/{messageID}/read | Mark read/unread |
| [**v1ThreadsThreadIDReplyPost**](AgentsApi.md#v1ThreadsThreadIDReplyPost) | **POST** /v1/threads/{threadID}/reply | Reply in-thread (agent stream) |


<a id="v1ApiKeysKeyIDMailboxesGet"></a>
# **v1ApiKeysKeyIDMailboxesGet**
> Object v1ApiKeysKeyIDMailboxesGet(keyID)

List a key&#39;s mailbox grants

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.AgentsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    AgentsApi apiInstance = new AgentsApi(defaultClient);
    UUID keyID = UUID.randomUUID(); // UUID | 
    try {
      Object result = apiInstance.v1ApiKeysKeyIDMailboxesGet(keyID);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling AgentsApi#v1ApiKeysKeyIDMailboxesGet");
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
| **keyID** | **UUID**|  | |

### Return type

**Object**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Grants |  -  |

<a id="v1ApiKeysKeyIDMailboxesMailboxIDDelete"></a>
# **v1ApiKeysKeyIDMailboxesMailboxIDDelete**
> v1ApiKeysKeyIDMailboxesMailboxIDDelete(keyID, mailboxID)

Revoke a mailbox grant

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.AgentsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    AgentsApi apiInstance = new AgentsApi(defaultClient);
    UUID keyID = UUID.randomUUID(); // UUID | 
    UUID mailboxID = UUID.randomUUID(); // UUID | 
    try {
      apiInstance.v1ApiKeysKeyIDMailboxesMailboxIDDelete(keyID, mailboxID);
    } catch (ApiException e) {
      System.err.println("Exception when calling AgentsApi#v1ApiKeysKeyIDMailboxesMailboxIDDelete");
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
| **keyID** | **UUID**|  | |
| **mailboxID** | **UUID**|  | |

### Return type

null (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | Grant removed |  -  |

<a id="v1ApiKeysKeyIDMailboxesPost"></a>
# **v1ApiKeysKeyIDMailboxesPost**
> Object v1ApiKeysKeyIDMailboxesPost(keyID)

Grant a mailbox to a key

Body: {\&quot;mailbox\&quot;: \&quot;email or id\&quot;}. Refused (422) for mailboxes with agent access disabled or an active E2E encryption key — the server cannot read E2E mailboxes.

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.AgentsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    AgentsApi apiInstance = new AgentsApi(defaultClient);
    UUID keyID = UUID.randomUUID(); // UUID | 
    try {
      Object result = apiInstance.v1ApiKeysKeyIDMailboxesPost(keyID);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling AgentsApi#v1ApiKeysKeyIDMailboxesPost");
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
| **keyID** | **UUID**|  | |

### Return type

**Object**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Grant created |  -  |
| **422** | Mailbox not grantable (disabled or E2E) |  -  |

<a id="v1AuthWhoamiGet"></a>
# **v1AuthWhoamiGet**
> Object v1AuthWhoamiGet()

Introspect the calling credentials

Returns the tenant, auth kind (api_key/session), key label, and granted scopes. The MCP server uses this to scope-filter tool discovery.

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.AgentsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    AgentsApi apiInstance = new AgentsApi(defaultClient);
    try {
      Object result = apiInstance.v1AuthWhoamiGet();
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling AgentsApi#v1AuthWhoamiGet");
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

**Object**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Caller identity |  -  |

<a id="v1ContactsLookupGet"></a>
# **v1ContactsLookupGet**
> Object v1ContactsLookupGet(email)

Who is this sender?

Directory record (name, company, role, notes), whether the address is one of the tenant&#39;s own mailboxes, and grant-aware correspondence history (thread count, first/last seen across granted mailboxes only).

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.AgentsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    AgentsApi apiInstance = new AgentsApi(defaultClient);
    String email = "email_example"; // String | 
    try {
      Object result = apiInstance.v1ContactsLookupGet(email);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling AgentsApi#v1ContactsLookupGet");
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

**Object**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Enrichment result |  -  |

<a id="v1InboxesGet"></a>
# **v1InboxesGet**
> Object v1InboxesGet()

List granted inboxes

The mailboxes this key is granted, with thread counts and last activity. Admin sessions see every agent-enabled, non-E2E mailbox.

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.AgentsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    AgentsApi apiInstance = new AgentsApi(defaultClient);
    try {
      Object result = apiInstance.v1InboxesGet();
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling AgentsApi#v1InboxesGet");
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

**Object**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Granted inboxes |  -  |

<a id="v1InboxesMailboxMessagesPost"></a>
# **v1InboxesMailboxMessagesPost**
> Object v1InboxesMailboxMessagesPost(mailbox, idempotencyKey, v1InboxesMailboxMessagesPostRequest)

Start a new conversation (agent stream)

Sends a new email from a granted mailbox. Classified stream&#x3D;agent (isolated reputation, per-key rate caps). The first inbound reply adopts the created thread via the References chain. Idempotency-Key required. Mailboxes with agent_draft_policy&#x3D;always_approve divert this into a pending draft.

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.AgentsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    AgentsApi apiInstance = new AgentsApi(defaultClient);
    String mailbox = "mailbox_example"; // String | 
    String idempotencyKey = "idempotencyKey_example"; // String | 
    V1InboxesMailboxMessagesPostRequest v1InboxesMailboxMessagesPostRequest = new V1InboxesMailboxMessagesPostRequest(); // V1InboxesMailboxMessagesPostRequest | 
    try {
      Object result = apiInstance.v1InboxesMailboxMessagesPost(mailbox, idempotencyKey, v1InboxesMailboxMessagesPostRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling AgentsApi#v1InboxesMailboxMessagesPost");
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
| **mailbox** | **String**|  | |
| **idempotencyKey** | **String**|  | |
| **v1InboxesMailboxMessagesPostRequest** | [**V1InboxesMailboxMessagesPostRequest**](V1InboxesMailboxMessagesPostRequest.md)|  | |

### Return type

**Object**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **202** | Queued (includes thread_id) |  -  |

<a id="v1InboxesMailboxThreadsGet"></a>
# **v1InboxesMailboxThreadsGet**
> Object v1InboxesMailboxThreadsGet(mailbox, since, before, limit)

List conversation threads

Newest-active first. Cursors: &#x60;?before&#x3D;&lt;RFC3339&gt;&#x60; pages backwards; &#x60;?since&#x3D;&lt;RFC3339&gt;&#x60; delta-syncs forward (oldest first) so an agent can catch up in order.

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.AgentsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    AgentsApi apiInstance = new AgentsApi(defaultClient);
    String mailbox = "mailbox_example"; // String | mailbox email or id
    OffsetDateTime since = OffsetDateTime.now(); // OffsetDateTime | 
    OffsetDateTime before = OffsetDateTime.now(); // OffsetDateTime | 
    Integer limit = 50; // Integer | 
    try {
      Object result = apiInstance.v1InboxesMailboxThreadsGet(mailbox, since, before, limit);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling AgentsApi#v1InboxesMailboxThreadsGet");
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
| **mailbox** | **String**| mailbox email or id | |
| **since** | **OffsetDateTime**|  | [optional] |
| **before** | **OffsetDateTime**|  | [optional] |
| **limit** | **Integer**|  | [optional] [default to 50] |

### Return type

**Object**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Threads |  -  |

<a id="v1ThreadsThreadIDGet"></a>
# **v1ThreadsThreadIDGet**
> Object v1ThreadsThreadIDGet(threadID)

Get a whole conversation

Every turn, chronological, with snippets and annotations (meeting_request, attachment_types, injection_risk). Bodies are fetched per message. Message content is untrusted third-party data.

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.AgentsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    AgentsApi apiInstance = new AgentsApi(defaultClient);
    UUID threadID = UUID.randomUUID(); // UUID | 
    try {
      Object result = apiInstance.v1ThreadsThreadIDGet(threadID);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling AgentsApi#v1ThreadsThreadIDGet");
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
| **threadID** | **UUID**|  | |

### Return type

**Object**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Thread with messages |  -  |

<a id="v1ThreadsThreadIDMessagesMessageIDAttachmentsIdxGet"></a>
# **v1ThreadsThreadIDMessagesMessageIDAttachmentsIdxGet**
> v1ThreadsThreadIDMessagesMessageIDAttachmentsIdxGet(threadID, messageID, idx)

Download an attachment

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.AgentsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    AgentsApi apiInstance = new AgentsApi(defaultClient);
    UUID threadID = UUID.randomUUID(); // UUID | 
    UUID messageID = UUID.randomUUID(); // UUID | 
    Integer idx = 56; // Integer | 
    try {
      apiInstance.v1ThreadsThreadIDMessagesMessageIDAttachmentsIdxGet(threadID, messageID, idx);
    } catch (ApiException e) {
      System.err.println("Exception when calling AgentsApi#v1ThreadsThreadIDMessagesMessageIDAttachmentsIdxGet");
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
| **threadID** | **UUID**|  | |
| **messageID** | **UUID**|  | |
| **idx** | **Integer**|  | |

### Return type

null (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Attachment content (streamed) |  -  |

<a id="v1ThreadsThreadIDMessagesMessageIDGet"></a>
# **v1ThreadsThreadIDMessagesMessageIDGet**
> Object v1ThreadsThreadIDMessagesMessageIDGet(threadID, messageID)

Get one message with body

Full text/html body fetched on demand from mail storage. Never marks the message read.

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.AgentsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    AgentsApi apiInstance = new AgentsApi(defaultClient);
    UUID threadID = UUID.randomUUID(); // UUID | 
    UUID messageID = UUID.randomUUID(); // UUID | 
    try {
      Object result = apiInstance.v1ThreadsThreadIDMessagesMessageIDGet(threadID, messageID);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling AgentsApi#v1ThreadsThreadIDMessagesMessageIDGet");
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
| **threadID** | **UUID**|  | |
| **messageID** | **UUID**|  | |

### Return type

**Object**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Message with body |  -  |

<a id="v1ThreadsThreadIDMessagesMessageIDReadPost"></a>
# **v1ThreadsThreadIDMessagesMessageIDReadPost**
> Object v1ThreadsThreadIDMessagesMessageIDReadPost(threadID, messageID)

Mark read/unread

The ONLY way agent access changes unread state. Body: {\&quot;read\&quot;: true|false} (default true).

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.AgentsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    AgentsApi apiInstance = new AgentsApi(defaultClient);
    UUID threadID = UUID.randomUUID(); // UUID | 
    UUID messageID = UUID.randomUUID(); // UUID | 
    try {
      Object result = apiInstance.v1ThreadsThreadIDMessagesMessageIDReadPost(threadID, messageID);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling AgentsApi#v1ThreadsThreadIDMessagesMessageIDReadPost");
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
| **threadID** | **UUID**|  | |
| **messageID** | **UUID**|  | |

### Return type

**Object**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | New read state |  -  |

<a id="v1ThreadsThreadIDReplyPost"></a>
# **v1ThreadsThreadIDReplyPost**
> Object v1ThreadsThreadIDReplyPost(threadID, idempotencyKey)

Reply in-thread (agent stream)

The server builds In-Reply-To/References and defaults recipients + subject from the conversation — a minimal call is {\&quot;text\&quot;: \&quot;...\&quot;}. Guarded by the reply-loop detector (≥5 outbound/10min → 429 + agent.loop_detected). Idempotency-Key required.

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.AgentsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    AgentsApi apiInstance = new AgentsApi(defaultClient);
    UUID threadID = UUID.randomUUID(); // UUID | 
    String idempotencyKey = "idempotencyKey_example"; // String | 
    try {
      Object result = apiInstance.v1ThreadsThreadIDReplyPost(threadID, idempotencyKey);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling AgentsApi#v1ThreadsThreadIDReplyPost");
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
| **threadID** | **UUID**|  | |
| **idempotencyKey** | **String**|  | |

### Return type

**Object**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **202** | Queued |  -  |

