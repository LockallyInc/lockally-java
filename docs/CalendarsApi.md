# CalendarsApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**addCalendarMember**](CalendarsApi.md#addCalendarMember) | **POST** /v1/calendars/{id}/members | Add a member to a calendar |
| [**createCalendar**](CalendarsApi.md#createCalendar) | **POST** /v1/calendars | Create a calendar |
| [**createCalendarEvent**](CalendarsApi.md#createCalendarEvent) | **POST** /v1/calendars/{id}/events | Create an event in a calendar |
| [**createCalendarIntegration**](CalendarsApi.md#createCalendarIntegration) | **POST** /v1/calendar-integrations | Create a calendar integration |
| [**deleteCalendar**](CalendarsApi.md#deleteCalendar) | **DELETE** /v1/calendars/{id} | Delete a calendar |
| [**deleteCalendarEvent**](CalendarsApi.md#deleteCalendarEvent) | **DELETE** /v1/calendars/{id}/events/{eventId} | Delete a calendar event |
| [**deleteCalendarIntegration**](CalendarsApi.md#deleteCalendarIntegration) | **DELETE** /v1/calendar-integrations/{id} | Delete a calendar integration |
| [**getCalendar**](CalendarsApi.md#getCalendar) | **GET** /v1/calendars/{id} | Get a calendar |
| [**getCalendarPolicies**](CalendarsApi.md#getCalendarPolicies) | **GET** /v1/calendar-policies | Get calendar policies |
| [**getCalendarSecurity**](CalendarsApi.md#getCalendarSecurity) | **GET** /v1/calendar-security | Get calendar security overview |
| [**listCalendarEvents**](CalendarsApi.md#listCalendarEvents) | **GET** /v1/calendars/{id}/events | List events in a calendar |
| [**listCalendarIntegrations**](CalendarsApi.md#listCalendarIntegrations) | **GET** /v1/calendar-integrations | List calendar integrations |
| [**listCalendarMembers**](CalendarsApi.md#listCalendarMembers) | **GET** /v1/calendars/{id}/members | List calendar members |
| [**listCalendars**](CalendarsApi.md#listCalendars) | **GET** /v1/calendars | List calendars |
| [**removeCalendarMember**](CalendarsApi.md#removeCalendarMember) | **DELETE** /v1/calendars/{id}/members/{memberId} | Remove a member from a calendar |
| [**syncCalendarIntegration**](CalendarsApi.md#syncCalendarIntegration) | **POST** /v1/calendar-integrations/{id}/sync | Trigger sync for a calendar integration |
| [**updateCalendar**](CalendarsApi.md#updateCalendar) | **PATCH** /v1/calendars/{id} | Update a calendar |
| [**updateCalendarEvent**](CalendarsApi.md#updateCalendarEvent) | **PATCH** /v1/calendars/{id}/events/{eventId} | Update a calendar event |
| [**updateCalendarIntegration**](CalendarsApi.md#updateCalendarIntegration) | **PATCH** /v1/calendar-integrations/{id} | Update a calendar integration |
| [**updateCalendarMember**](CalendarsApi.md#updateCalendarMember) | **PATCH** /v1/calendars/{id}/members/{memberId} | Update a calendar member&#39;s role |
| [**updateCalendarPolicies**](CalendarsApi.md#updateCalendarPolicies) | **PATCH** /v1/calendar-policies | Update calendar policies |


<a id="addCalendarMember"></a>
# **addCalendarMember**
> CalendarMember addCalendarMember(id, addCalendarMemberRequest)

Add a member to a calendar

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.CalendarsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    CalendarsApi apiInstance = new CalendarsApi(defaultClient);
    UUID id = UUID.randomUUID(); // UUID | 
    AddCalendarMemberRequest addCalendarMemberRequest = new AddCalendarMemberRequest(); // AddCalendarMemberRequest | 
    try {
      CalendarMember result = apiInstance.addCalendarMember(id, addCalendarMemberRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling CalendarsApi#addCalendarMember");
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
| **addCalendarMemberRequest** | [**AddCalendarMemberRequest**](AddCalendarMemberRequest.md)|  | |

### Return type

[**CalendarMember**](CalendarMember.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Member added |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

<a id="createCalendar"></a>
# **createCalendar**
> Calendar createCalendar(createCalendarRequest)

Create a calendar

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.CalendarsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    CalendarsApi apiInstance = new CalendarsApi(defaultClient);
    CreateCalendarRequest createCalendarRequest = new CreateCalendarRequest(); // CreateCalendarRequest | 
    try {
      Calendar result = apiInstance.createCalendar(createCalendarRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling CalendarsApi#createCalendar");
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
| **createCalendarRequest** | [**CreateCalendarRequest**](CreateCalendarRequest.md)|  | |

### Return type

[**Calendar**](Calendar.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Calendar created |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

<a id="createCalendarEvent"></a>
# **createCalendarEvent**
> CalendarEvent createCalendarEvent(id, createCalendarEventRequest)

Create an event in a calendar

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.CalendarsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    CalendarsApi apiInstance = new CalendarsApi(defaultClient);
    UUID id = UUID.randomUUID(); // UUID | 
    CreateCalendarEventRequest createCalendarEventRequest = new CreateCalendarEventRequest(); // CreateCalendarEventRequest | 
    try {
      CalendarEvent result = apiInstance.createCalendarEvent(id, createCalendarEventRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling CalendarsApi#createCalendarEvent");
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
| **createCalendarEventRequest** | [**CreateCalendarEventRequest**](CreateCalendarEventRequest.md)|  | |

### Return type

[**CalendarEvent**](CalendarEvent.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Event created |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

<a id="createCalendarIntegration"></a>
# **createCalendarIntegration**
> CalendarIntegration createCalendarIntegration(createCalendarIntegrationRequest)

Create a calendar integration

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.CalendarsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    CalendarsApi apiInstance = new CalendarsApi(defaultClient);
    CreateCalendarIntegrationRequest createCalendarIntegrationRequest = new CreateCalendarIntegrationRequest(); // CreateCalendarIntegrationRequest | 
    try {
      CalendarIntegration result = apiInstance.createCalendarIntegration(createCalendarIntegrationRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling CalendarsApi#createCalendarIntegration");
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
| **createCalendarIntegrationRequest** | [**CreateCalendarIntegrationRequest**](CreateCalendarIntegrationRequest.md)|  | |

### Return type

[**CalendarIntegration**](CalendarIntegration.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Integration created |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

<a id="deleteCalendar"></a>
# **deleteCalendar**
> deleteCalendar(id)

Delete a calendar

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.CalendarsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    CalendarsApi apiInstance = new CalendarsApi(defaultClient);
    UUID id = UUID.randomUUID(); // UUID | 
    try {
      apiInstance.deleteCalendar(id);
    } catch (ApiException e) {
      System.err.println("Exception when calling CalendarsApi#deleteCalendar");
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
| **204** | No content |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

<a id="deleteCalendarEvent"></a>
# **deleteCalendarEvent**
> deleteCalendarEvent(id, eventId)

Delete a calendar event

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.CalendarsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    CalendarsApi apiInstance = new CalendarsApi(defaultClient);
    UUID id = UUID.randomUUID(); // UUID | 
    UUID eventId = UUID.randomUUID(); // UUID | 
    try {
      apiInstance.deleteCalendarEvent(id, eventId);
    } catch (ApiException e) {
      System.err.println("Exception when calling CalendarsApi#deleteCalendarEvent");
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
| **eventId** | **UUID**|  | |

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

<a id="deleteCalendarIntegration"></a>
# **deleteCalendarIntegration**
> deleteCalendarIntegration(id)

Delete a calendar integration

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.CalendarsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    CalendarsApi apiInstance = new CalendarsApi(defaultClient);
    UUID id = UUID.randomUUID(); // UUID | 
    try {
      apiInstance.deleteCalendarIntegration(id);
    } catch (ApiException e) {
      System.err.println("Exception when calling CalendarsApi#deleteCalendarIntegration");
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
| **204** | No content |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

<a id="getCalendar"></a>
# **getCalendar**
> Calendar getCalendar(id)

Get a calendar

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.CalendarsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    CalendarsApi apiInstance = new CalendarsApi(defaultClient);
    UUID id = UUID.randomUUID(); // UUID | 
    try {
      Calendar result = apiInstance.getCalendar(id);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling CalendarsApi#getCalendar");
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

[**Calendar**](Calendar.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Calendar details |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

<a id="getCalendarPolicies"></a>
# **getCalendarPolicies**
> CalendarPolicies getCalendarPolicies()

Get calendar policies

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.CalendarsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    CalendarsApi apiInstance = new CalendarsApi(defaultClient);
    try {
      CalendarPolicies result = apiInstance.getCalendarPolicies();
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling CalendarsApi#getCalendarPolicies");
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

[**CalendarPolicies**](CalendarPolicies.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Calendar policies |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

<a id="getCalendarSecurity"></a>
# **getCalendarSecurity**
> GetCalendarSecurity200Response getCalendarSecurity()

Get calendar security overview

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.CalendarsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    CalendarsApi apiInstance = new CalendarsApi(defaultClient);
    try {
      GetCalendarSecurity200Response result = apiInstance.getCalendarSecurity();
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling CalendarsApi#getCalendarSecurity");
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

[**GetCalendarSecurity200Response**](GetCalendarSecurity200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Calendar security overview |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

<a id="listCalendarEvents"></a>
# **listCalendarEvents**
> ListCalendarEvents200Response listCalendarEvents(id, from, to)

List events in a calendar

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.CalendarsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    CalendarsApi apiInstance = new CalendarsApi(defaultClient);
    UUID id = UUID.randomUUID(); // UUID | 
    OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | 
    OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | 
    try {
      ListCalendarEvents200Response result = apiInstance.listCalendarEvents(id, from, to);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling CalendarsApi#listCalendarEvents");
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
| **from** | **OffsetDateTime**|  | [optional] |
| **to** | **OffsetDateTime**|  | [optional] |

### Return type

[**ListCalendarEvents200Response**](ListCalendarEvents200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List of calendar events |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

<a id="listCalendarIntegrations"></a>
# **listCalendarIntegrations**
> ListCalendarIntegrations200Response listCalendarIntegrations()

List calendar integrations

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.CalendarsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    CalendarsApi apiInstance = new CalendarsApi(defaultClient);
    try {
      ListCalendarIntegrations200Response result = apiInstance.listCalendarIntegrations();
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling CalendarsApi#listCalendarIntegrations");
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

[**ListCalendarIntegrations200Response**](ListCalendarIntegrations200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List of calendar integrations |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

<a id="listCalendarMembers"></a>
# **listCalendarMembers**
> ListCalendarMembers200Response listCalendarMembers(id)

List calendar members

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.CalendarsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    CalendarsApi apiInstance = new CalendarsApi(defaultClient);
    UUID id = UUID.randomUUID(); // UUID | 
    try {
      ListCalendarMembers200Response result = apiInstance.listCalendarMembers(id);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling CalendarsApi#listCalendarMembers");
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

[**ListCalendarMembers200Response**](ListCalendarMembers200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List of calendar members |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

<a id="listCalendars"></a>
# **listCalendars**
> ListCalendars200Response listCalendars()

List calendars

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.CalendarsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    CalendarsApi apiInstance = new CalendarsApi(defaultClient);
    try {
      ListCalendars200Response result = apiInstance.listCalendars();
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling CalendarsApi#listCalendars");
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

[**ListCalendars200Response**](ListCalendars200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List of calendars |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

<a id="removeCalendarMember"></a>
# **removeCalendarMember**
> removeCalendarMember(id, memberId)

Remove a member from a calendar

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.CalendarsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    CalendarsApi apiInstance = new CalendarsApi(defaultClient);
    UUID id = UUID.randomUUID(); // UUID | 
    UUID memberId = UUID.randomUUID(); // UUID | 
    try {
      apiInstance.removeCalendarMember(id, memberId);
    } catch (ApiException e) {
      System.err.println("Exception when calling CalendarsApi#removeCalendarMember");
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
| **memberId** | **UUID**|  | |

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

<a id="syncCalendarIntegration"></a>
# **syncCalendarIntegration**
> CalendarIntegration syncCalendarIntegration(id)

Trigger sync for a calendar integration

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.CalendarsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    CalendarsApi apiInstance = new CalendarsApi(defaultClient);
    UUID id = UUID.randomUUID(); // UUID | 
    try {
      CalendarIntegration result = apiInstance.syncCalendarIntegration(id);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling CalendarsApi#syncCalendarIntegration");
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

[**CalendarIntegration**](CalendarIntegration.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Sync initiated |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

<a id="updateCalendar"></a>
# **updateCalendar**
> Calendar updateCalendar(id, updateCalendarRequest)

Update a calendar

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.CalendarsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    CalendarsApi apiInstance = new CalendarsApi(defaultClient);
    UUID id = UUID.randomUUID(); // UUID | 
    UpdateCalendarRequest updateCalendarRequest = new UpdateCalendarRequest(); // UpdateCalendarRequest | 
    try {
      Calendar result = apiInstance.updateCalendar(id, updateCalendarRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling CalendarsApi#updateCalendar");
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
| **updateCalendarRequest** | [**UpdateCalendarRequest**](UpdateCalendarRequest.md)|  | |

### Return type

[**Calendar**](Calendar.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Calendar updated |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

<a id="updateCalendarEvent"></a>
# **updateCalendarEvent**
> CalendarEvent updateCalendarEvent(id, eventId, updateCalendarEventRequest)

Update a calendar event

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.CalendarsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    CalendarsApi apiInstance = new CalendarsApi(defaultClient);
    UUID id = UUID.randomUUID(); // UUID | 
    UUID eventId = UUID.randomUUID(); // UUID | 
    UpdateCalendarEventRequest updateCalendarEventRequest = new UpdateCalendarEventRequest(); // UpdateCalendarEventRequest | 
    try {
      CalendarEvent result = apiInstance.updateCalendarEvent(id, eventId, updateCalendarEventRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling CalendarsApi#updateCalendarEvent");
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
| **eventId** | **UUID**|  | |
| **updateCalendarEventRequest** | [**UpdateCalendarEventRequest**](UpdateCalendarEventRequest.md)|  | |

### Return type

[**CalendarEvent**](CalendarEvent.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Event updated |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

<a id="updateCalendarIntegration"></a>
# **updateCalendarIntegration**
> CalendarIntegration updateCalendarIntegration(id, updateCalendarIntegrationRequest)

Update a calendar integration

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.CalendarsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    CalendarsApi apiInstance = new CalendarsApi(defaultClient);
    UUID id = UUID.randomUUID(); // UUID | 
    UpdateCalendarIntegrationRequest updateCalendarIntegrationRequest = new UpdateCalendarIntegrationRequest(); // UpdateCalendarIntegrationRequest | 
    try {
      CalendarIntegration result = apiInstance.updateCalendarIntegration(id, updateCalendarIntegrationRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling CalendarsApi#updateCalendarIntegration");
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
| **updateCalendarIntegrationRequest** | [**UpdateCalendarIntegrationRequest**](UpdateCalendarIntegrationRequest.md)|  | |

### Return type

[**CalendarIntegration**](CalendarIntegration.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Integration updated |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

<a id="updateCalendarMember"></a>
# **updateCalendarMember**
> CalendarMember updateCalendarMember(id, memberId, updateCalendarMemberRequest)

Update a calendar member&#39;s role

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.CalendarsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    CalendarsApi apiInstance = new CalendarsApi(defaultClient);
    UUID id = UUID.randomUUID(); // UUID | 
    UUID memberId = UUID.randomUUID(); // UUID | 
    UpdateCalendarMemberRequest updateCalendarMemberRequest = new UpdateCalendarMemberRequest(); // UpdateCalendarMemberRequest | 
    try {
      CalendarMember result = apiInstance.updateCalendarMember(id, memberId, updateCalendarMemberRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling CalendarsApi#updateCalendarMember");
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
| **memberId** | **UUID**|  | |
| **updateCalendarMemberRequest** | [**UpdateCalendarMemberRequest**](UpdateCalendarMemberRequest.md)|  | |

### Return type

[**CalendarMember**](CalendarMember.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Member updated |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

<a id="updateCalendarPolicies"></a>
# **updateCalendarPolicies**
> CalendarPolicies updateCalendarPolicies(updateCalendarPoliciesRequest)

Update calendar policies

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.auth.*;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.CalendarsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    CalendarsApi apiInstance = new CalendarsApi(defaultClient);
    UpdateCalendarPoliciesRequest updateCalendarPoliciesRequest = new UpdateCalendarPoliciesRequest(); // UpdateCalendarPoliciesRequest | 
    try {
      CalendarPolicies result = apiInstance.updateCalendarPolicies(updateCalendarPoliciesRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling CalendarsApi#updateCalendarPolicies");
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
| **updateCalendarPoliciesRequest** | [**UpdateCalendarPoliciesRequest**](UpdateCalendarPoliciesRequest.md)|  | |

### Return type

[**CalendarPolicies**](CalendarPolicies.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Calendar policies updated |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

