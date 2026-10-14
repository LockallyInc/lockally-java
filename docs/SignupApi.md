# SignupApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**signup**](SignupApi.md#signup) | **POST** /v1/signup | Sign up a new tenant |


<a id="signup"></a>
# **signup**
> V1AdminLoginPost200Response signup(signupRequest)

Sign up a new tenant

### Example
```java
// Import classes:
import com.lockally.sdk.ApiClient;
import com.lockally.sdk.ApiException;
import com.lockally.sdk.Configuration;
import com.lockally.sdk.models.*;
import com.lockally.sdk.api.SignupApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.lockally.com");

    SignupApi apiInstance = new SignupApi(defaultClient);
    SignupRequest signupRequest = new SignupRequest(); // SignupRequest | 
    try {
      V1AdminLoginPost200Response result = apiInstance.signup(signupRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling SignupApi#signup");
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
| **signupRequest** | [**SignupRequest**](SignupRequest.md)|  | |

### Return type

[**V1AdminLoginPost200Response**](V1AdminLoginPost200Response.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Tenant created with initial admin and API token. |  -  |
| **400** | Malformed request. |  -  |
| **409** | Slug or email already taken. |  -  |

