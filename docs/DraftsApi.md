# DraftsApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**v1DraftsDraftIDApprovePost**](DraftsApi.md#v1DraftsDraftIDApprovePost) | **POST** /v1/drafts/{draftID}/approve | Approve a pending draft (human) |
| [**v1DraftsDraftIDCancelPost**](DraftsApi.md#v1DraftsDraftIDCancelPost) | **POST** /v1/drafts/{draftID}/cancel | Withdraw a pending draft |
| [**v1DraftsDraftIDGet**](DraftsApi.md#v1DraftsDraftIDGet) | **GET** /v1/drafts/{draftID} | Get a draft |
| [**v1DraftsDraftIDRejectPost**](DraftsApi.md#v1DraftsDraftIDRejectPost) | **POST** /v1/drafts/{draftID}/reject | Reject a pending draft (human) |
| [**v1DraftsGet**](DraftsApi.md#v1DraftsGet) | **GET** /v1/drafts | List drafts |
| [**v1InboxesMailboxDraftsPost**](DraftsApi.md#v1InboxesMailboxDraftsPost) | **POST** /v1/inboxes/{mailbox}/drafts | Propose a new conversation as a draft |
| [**v1ThreadsThreadIDDraftsPost**](DraftsApi.md#v1ThreadsThreadIDDraftsPost) | **POST** /v1/threads/{threadID}/drafts | Propose a reply as a draft |


<a id="v1DraftsDraftIDApprovePost"></a>
# **v1DraftsDraftIDApprovePost**
> Object v1DraftsDraftIDApprovePost(draftID)

Approve a pending draft (human)

Sends the draft exactly as reviewed, through the agent stream (loop detector included). Fires draft.approved.

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.DraftsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    DraftsApi apiInstance = new DraftsApi(defaultClient);
    UUID draftID = UUID.randomUUID(); // UUID | 
    try {
      Object result = apiInstance.v1DraftsDraftIDApprovePost(draftID);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling DraftsApi#v1DraftsDraftIDApprovePost");
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
| **draftID** | **UUID**|  | |

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
| **200** | Sent |  -  |

<a id="v1DraftsDraftIDCancelPost"></a>
# **v1DraftsDraftIDCancelPost**
> Object v1DraftsDraftIDCancelPost(draftID)

Withdraw a pending draft

Only the API key that created the draft may cancel it.

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.DraftsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    DraftsApi apiInstance = new DraftsApi(defaultClient);
    UUID draftID = UUID.randomUUID(); // UUID | 
    try {
      Object result = apiInstance.v1DraftsDraftIDCancelPost(draftID);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling DraftsApi#v1DraftsDraftIDCancelPost");
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
| **draftID** | **UUID**|  | |

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
| **200** | Cancelled |  -  |

<a id="v1DraftsDraftIDGet"></a>
# **v1DraftsDraftIDGet**
> Object v1DraftsDraftIDGet(draftID)

Get a draft

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.DraftsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    DraftsApi apiInstance = new DraftsApi(defaultClient);
    UUID draftID = UUID.randomUUID(); // UUID | 
    try {
      Object result = apiInstance.v1DraftsDraftIDGet(draftID);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling DraftsApi#v1DraftsDraftIDGet");
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
| **draftID** | **UUID**|  | |

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
| **200** | Draft |  -  |

<a id="v1DraftsDraftIDRejectPost"></a>
# **v1DraftsDraftIDRejectPost**
> Object v1DraftsDraftIDRejectPost(draftID)

Reject a pending draft (human)

Body: {\&quot;reason\&quot;: \&quot;...\&quot;} (optional). Fires draft.rejected.

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.DraftsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    DraftsApi apiInstance = new DraftsApi(defaultClient);
    UUID draftID = UUID.randomUUID(); // UUID | 
    try {
      Object result = apiInstance.v1DraftsDraftIDRejectPost(draftID);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling DraftsApi#v1DraftsDraftIDRejectPost");
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
| **draftID** | **UUID**|  | |

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
| **200** | Rejected |  -  |

<a id="v1DraftsGet"></a>
# **v1DraftsGet**
> Object v1DraftsGet(status, limit)

List drafts

Filter with ?status&#x3D;pending_approval|sent|rejected|cancelled. Keys see drafts of granted mailboxes; admin sessions see all.

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.DraftsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    DraftsApi apiInstance = new DraftsApi(defaultClient);
    String status = "status_example"; // String | 
    Integer limit = 50; // Integer | 
    try {
      Object result = apiInstance.v1DraftsGet(status, limit);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling DraftsApi#v1DraftsGet");
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
| **status** | **String**|  | [optional] |
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
| **200** | Drafts |  -  |

<a id="v1InboxesMailboxDraftsPost"></a>
# **v1InboxesMailboxDraftsPost**
> Object v1InboxesMailboxDraftsPost(mailbox, idempotencyKey)

Propose a new conversation as a draft

New-conversation drafts ALWAYS require human approval (policy flag new_thread). Idempotency-Key required.

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.DraftsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    DraftsApi apiInstance = new DraftsApi(defaultClient);
    String mailbox = "mailbox_example"; // String | 
    String idempotencyKey = "idempotencyKey_example"; // String | 
    try {
      Object result = apiInstance.v1InboxesMailboxDraftsPost(mailbox, idempotencyKey);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling DraftsApi#v1InboxesMailboxDraftsPost");
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
| **202** | Draft outcome (pending_approval) |  -  |

<a id="v1ThreadsThreadIDDraftsPost"></a>
# **v1ThreadsThreadIDDraftsPost**
> Object v1ThreadsThreadIDDraftsPost(threadID, idempotencyKey)

Propose a reply as a draft

The safe default over /reply: the deterministic policy engine auto-sends clean in-thread replies and holds anything risky (PII, new recipients, injection-flagged threads, always-approve mailboxes) for human approval. Fires draft.pending_approval when held. Idempotency-Key required.

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.DraftsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    DraftsApi apiInstance = new DraftsApi(defaultClient);
    UUID threadID = UUID.randomUUID(); // UUID | 
    String idempotencyKey = "idempotencyKey_example"; // String | 
    try {
      Object result = apiInstance.v1ThreadsThreadIDDraftsPost(threadID, idempotencyKey);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling DraftsApi#v1ThreadsThreadIDDraftsPost");
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
| **202** | Outcome (sent | pending_approval) with policy_flags |  -  |

