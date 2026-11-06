# ContactsApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**bulkUpsertExternalContacts**](ContactsApi.md#bulkUpsertExternalContacts) | **PUT** /v1/contacts/external/{system} | Create or update up to 500 contacts by their ids in another system |
| [**createContact**](ContactsApi.md#createContact) | **POST** /v1/contacts | Create a contact |
| [**deleteContact**](ContactsApi.md#deleteContact) | **DELETE** /v1/contacts/{id} | Delete a contact |
| [**deleteExternalContact**](ContactsApi.md#deleteExternalContact) | **DELETE** /v1/contacts/external/{system}/{external_id} | Delete a contact by its id in another system |
| [**getContact**](ContactsApi.md#getContact) | **GET** /v1/contacts/{id} | Get a contact |
| [**getContactLists**](ContactsApi.md#getContactLists) | **GET** /v1/contacts/{id}/lists | Get lists a contact belongs to |
| [**getExternalContact**](ContactsApi.md#getExternalContact) | **GET** /v1/contacts/external/{system}/{external_id} | Get a contact by its id in another system |
| [**listContacts**](ContactsApi.md#listContacts) | **GET** /v1/contacts | List contacts |
| [**updateContact**](ContactsApi.md#updateContact) | **PATCH** /v1/contacts/{id} | Update a contact |
| [**upsertExternalContact**](ContactsApi.md#upsertExternalContact) | **PUT** /v1/contacts/external/{system}/{external_id} | Create or update a contact by its id in another system |


<a id="bulkUpsertExternalContacts"></a>
# **bulkUpsertExternalContacts**
> BulkUpsertExternalContacts200Response bulkUpsertExternalContacts(system, bulkUpsertExternalContactsRequest)

Create or update up to 500 contacts by their ids in another system

For a sync. Each row stands alone: a bad row is reported in &#x60;results&#x60; with its index and the rest are stored, so the response is 200 whenever the request itself is well formed. Read &#x60;failed&#x60; and &#x60;results&#x60;. Two rows with the same &#x60;external_id&#x60; in one request are refused (the later one), because which is current cannot be known. Rerunning the same payload updates rather than duplicates.

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.ContactsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    ContactsApi apiInstance = new ContactsApi(defaultClient);
    String system = "system_example"; // String | 
    BulkUpsertExternalContactsRequest bulkUpsertExternalContactsRequest = new BulkUpsertExternalContactsRequest(); // BulkUpsertExternalContactsRequest | 
    try {
      BulkUpsertExternalContacts200Response result = apiInstance.bulkUpsertExternalContacts(system, bulkUpsertExternalContactsRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling ContactsApi#bulkUpsertExternalContacts");
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
| **system** | **String**|  | |
| **bulkUpsertExternalContactsRequest** | [**BulkUpsertExternalContactsRequest**](BulkUpsertExternalContactsRequest.md)|  | |

### Return type

[**BulkUpsertExternalContacts200Response**](BulkUpsertExternalContacts200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Per-row results |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

<a id="createContact"></a>
# **createContact**
> Contact createContact(createContactRequest)

Create a contact

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.ContactsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    ContactsApi apiInstance = new ContactsApi(defaultClient);
    CreateContactRequest createContactRequest = new CreateContactRequest(); // CreateContactRequest | 
    try {
      Contact result = apiInstance.createContact(createContactRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling ContactsApi#createContact");
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
| **createContactRequest** | [**CreateContactRequest**](CreateContactRequest.md)|  | |

### Return type

[**Contact**](Contact.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Contact created |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

<a id="deleteContact"></a>
# **deleteContact**
> deleteContact(id)

Delete a contact

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.ContactsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    ContactsApi apiInstance = new ContactsApi(defaultClient);
    UUID id = UUID.randomUUID(); // UUID | 
    try {
      apiInstance.deleteContact(id);
    } catch (ApiException e) {
      System.err.println("Exception when calling ContactsApi#deleteContact");
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
| **204** | Contact deleted |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

<a id="deleteExternalContact"></a>
# **deleteExternalContact**
> deleteExternalContact(system, externalId)

Delete a contact by its id in another system

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.ContactsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    ContactsApi apiInstance = new ContactsApi(defaultClient);
    String system = "system_example"; // String | Your label for the system the record comes from, for example `salesforce`, `hubspot` or `odoo`. 1 to 64 characters: lowercase letters, digits, dot, underscore or hyphen (upper case is folded).
    String externalId = "externalId_example"; // String | The record's id in that system, kept exactly as given (case matters). 1 to 255 characters, no spaces. URL-encode it.
    try {
      apiInstance.deleteExternalContact(system, externalId);
    } catch (ApiException e) {
      System.err.println("Exception when calling ContactsApi#deleteExternalContact");
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
| **system** | **String**| Your label for the system the record comes from, for example &#x60;salesforce&#x60;, &#x60;hubspot&#x60; or &#x60;odoo&#x60;. 1 to 64 characters: lowercase letters, digits, dot, underscore or hyphen (upper case is folded). | |
| **externalId** | **String**| The record&#39;s id in that system, kept exactly as given (case matters). 1 to 255 characters, no spaces. URL-encode it. | |

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
| **204** | Contact deleted |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

<a id="getContact"></a>
# **getContact**
> Contact getContact(id)

Get a contact

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.ContactsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    ContactsApi apiInstance = new ContactsApi(defaultClient);
    UUID id = UUID.randomUUID(); // UUID | 
    try {
      Contact result = apiInstance.getContact(id);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling ContactsApi#getContact");
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

[**Contact**](Contact.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Contact details |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

<a id="getContactLists"></a>
# **getContactLists**
> GetContactLists200Response getContactLists(id)

Get lists a contact belongs to

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.ContactsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    ContactsApi apiInstance = new ContactsApi(defaultClient);
    UUID id = UUID.randomUUID(); // UUID | 
    try {
      GetContactLists200Response result = apiInstance.getContactLists(id);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling ContactsApi#getContactLists");
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

[**GetContactLists200Response**](GetContactLists200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Lists containing this contact |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

<a id="getExternalContact"></a>
# **getExternalContact**
> Contact getExternalContact(system, externalId)

Get a contact by its id in another system

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.ContactsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    ContactsApi apiInstance = new ContactsApi(defaultClient);
    String system = "system_example"; // String | Your label for the system the record comes from, for example `salesforce`, `hubspot` or `odoo`. 1 to 64 characters: lowercase letters, digits, dot, underscore or hyphen (upper case is folded).
    String externalId = "externalId_example"; // String | The record's id in that system, kept exactly as given (case matters). 1 to 255 characters, no spaces. URL-encode it.
    try {
      Contact result = apiInstance.getExternalContact(system, externalId);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling ContactsApi#getExternalContact");
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
| **system** | **String**| Your label for the system the record comes from, for example &#x60;salesforce&#x60;, &#x60;hubspot&#x60; or &#x60;odoo&#x60;. 1 to 64 characters: lowercase letters, digits, dot, underscore or hyphen (upper case is folded). | |
| **externalId** | **String**| The record&#39;s id in that system, kept exactly as given (case matters). 1 to 255 characters, no spaces. URL-encode it. | |

### Return type

[**Contact**](Contact.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Contact details |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

<a id="listContacts"></a>
# **listContacts**
> ListContacts200Response listContacts(q, type, department, status, source)

List contacts

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.ContactsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    ContactsApi apiInstance = new ContactsApi(defaultClient);
    String q = "q_example"; // String | Free-text search across name, email, company
    String type = "type_example"; // String | Filter by contact_type
    String department = "department_example"; // String | Filter by department
    String status = "status_example"; // String | Filter by status
    String source = "source_example"; // String | Filter by source
    try {
      ListContacts200Response result = apiInstance.listContacts(q, type, department, status, source);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling ContactsApi#listContacts");
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
| **q** | **String**| Free-text search across name, email, company | [optional] |
| **type** | **String**| Filter by contact_type | [optional] |
| **department** | **String**| Filter by department | [optional] |
| **status** | **String**| Filter by status | [optional] |
| **source** | **String**| Filter by source | [optional] |

### Return type

[**ListContacts200Response**](ListContacts200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List of contacts |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

<a id="updateContact"></a>
# **updateContact**
> Contact updateContact(id, updateContactRequest)

Update a contact

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.ContactsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    ContactsApi apiInstance = new ContactsApi(defaultClient);
    UUID id = UUID.randomUUID(); // UUID | 
    UpdateContactRequest updateContactRequest = new UpdateContactRequest(); // UpdateContactRequest | 
    try {
      Contact result = apiInstance.updateContact(id, updateContactRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling ContactsApi#updateContact");
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
| **updateContactRequest** | [**UpdateContactRequest**](UpdateContactRequest.md)|  | |

### Return type

[**Contact**](Contact.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Contact updated |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

<a id="upsertExternalContact"></a>
# **upsertExternalContact**
> Contact upsertExternalContact(system, externalId, externalContactInput)

Create or update a contact by its id in another system

Idempotent: the path is the identity, so sending the same request twice cannot create a second contact, and you never need to store our id. Returns 201 when the contact was created and 200 when it already existed. The body is the full representation: a field you leave out is cleared. Email is an ordinary attribute, not a key, so changing it updates the same contact. &#x60;mailboxes:write&#x60; is also accepted.

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.ContactsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    ContactsApi apiInstance = new ContactsApi(defaultClient);
    String system = "system_example"; // String | Your label for the system the record comes from, for example `salesforce`, `hubspot` or `odoo`. 1 to 64 characters: lowercase letters, digits, dot, underscore or hyphen (upper case is folded).
    String externalId = "externalId_example"; // String | The record's id in that system, kept exactly as given (case matters). 1 to 255 characters, no spaces. URL-encode it.
    ExternalContactInput externalContactInput = new ExternalContactInput(); // ExternalContactInput | 
    try {
      Contact result = apiInstance.upsertExternalContact(system, externalId, externalContactInput);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling ContactsApi#upsertExternalContact");
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
| **system** | **String**| Your label for the system the record comes from, for example &#x60;salesforce&#x60;, &#x60;hubspot&#x60; or &#x60;odoo&#x60;. 1 to 64 characters: lowercase letters, digits, dot, underscore or hyphen (upper case is folded). | |
| **externalId** | **String**| The record&#39;s id in that system, kept exactly as given (case matters). 1 to 255 characters, no spaces. URL-encode it. | |
| **externalContactInput** | [**ExternalContactInput**](ExternalContactInput.md)|  | |

### Return type

[**Contact**](Contact.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The contact already existed and was updated |  -  |
| **201** | The contact was created |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

