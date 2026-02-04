# IntegrationsApi

All URIs are relative to *https://api.pdftemplateapi.com*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**deleteS3Config**](IntegrationsApi.md#deleteS3Config) | **DELETE** /v1/integrations/s3 | Delete S3 configuration |
| [**deleteS3ConfigWithHttpInfo**](IntegrationsApi.md#deleteS3ConfigWithHttpInfo) | **DELETE** /v1/integrations/s3 | Delete S3 configuration |
| [**getS3Config**](IntegrationsApi.md#getS3Config) | **GET** /v1/integrations/s3 | Get S3 configuration |
| [**getS3ConfigWithHttpInfo**](IntegrationsApi.md#getS3ConfigWithHttpInfo) | **GET** /v1/integrations/s3 | Get S3 configuration |
| [**saveS3Config**](IntegrationsApi.md#saveS3Config) | **POST** /v1/integrations/s3 | Save S3 configuration |
| [**saveS3ConfigWithHttpInfo**](IntegrationsApi.md#saveS3ConfigWithHttpInfo) | **POST** /v1/integrations/s3 | Save S3 configuration |
| [**testS3Connection**](IntegrationsApi.md#testS3Connection) | **POST** /v1/integrations/s3/test | Test S3 connection |
| [**testS3ConnectionWithHttpInfo**](IntegrationsApi.md#testS3ConnectionWithHttpInfo) | **POST** /v1/integrations/s3/test | Test S3 connection |



## deleteS3Config

> S3SuccessResponse deleteS3Config()

Delete S3 configuration

Delete S3 storage configuration.  **Authentication:** API Key required (&#x60;x-api-key&#x60; header) with admin privileges  **Usage:** Remove your S3 integration. Generated PDFs will use the default CDN storage after deletion.  **Warning:** This action is irreversible. You&#39;ll need to reconfigure S3 to use it again.  **No credits consumed:** This is a configuration endpoint.

### Example

```java
// Import classes:
import com.templatefox.sdk.ApiClient;
import com.templatefox.sdk.ApiException;
import com.templatefox.sdk.Configuration;
import com.templatefox.sdk.auth.*;
import com.templatefox.sdk.models.*;
import com.templatefox.sdk.api.IntegrationsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.pdftemplateapi.com");
        
        // Configure API key authorization: ApiKeyAuth
        ApiKeyAuth ApiKeyAuth = (ApiKeyAuth) defaultClient.getAuthentication("ApiKeyAuth");
        ApiKeyAuth.setApiKey("YOUR API KEY");
        // Uncomment the following line to set a prefix for the API key, e.g. "Token" (defaults to null)
        //ApiKeyAuth.setApiKeyPrefix("Token");

        IntegrationsApi apiInstance = new IntegrationsApi(defaultClient);
        try {
            S3SuccessResponse result = apiInstance.deleteS3Config();
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling IntegrationsApi#deleteS3Config");
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

[**S3SuccessResponse**](S3SuccessResponse.md)


### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Configuration deleted successfully |  -  |
| **403** | Admin privileges required |  -  |
| **422** | Validation Error |  -  |

## deleteS3ConfigWithHttpInfo

> ApiResponse<S3SuccessResponse> deleteS3Config deleteS3ConfigWithHttpInfo()

Delete S3 configuration

Delete S3 storage configuration.  **Authentication:** API Key required (&#x60;x-api-key&#x60; header) with admin privileges  **Usage:** Remove your S3 integration. Generated PDFs will use the default CDN storage after deletion.  **Warning:** This action is irreversible. You&#39;ll need to reconfigure S3 to use it again.  **No credits consumed:** This is a configuration endpoint.

### Example

```java
// Import classes:
import com.templatefox.sdk.ApiClient;
import com.templatefox.sdk.ApiException;
import com.templatefox.sdk.ApiResponse;
import com.templatefox.sdk.Configuration;
import com.templatefox.sdk.auth.*;
import com.templatefox.sdk.models.*;
import com.templatefox.sdk.api.IntegrationsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.pdftemplateapi.com");
        
        // Configure API key authorization: ApiKeyAuth
        ApiKeyAuth ApiKeyAuth = (ApiKeyAuth) defaultClient.getAuthentication("ApiKeyAuth");
        ApiKeyAuth.setApiKey("YOUR API KEY");
        // Uncomment the following line to set a prefix for the API key, e.g. "Token" (defaults to null)
        //ApiKeyAuth.setApiKeyPrefix("Token");

        IntegrationsApi apiInstance = new IntegrationsApi(defaultClient);
        try {
            ApiResponse<S3SuccessResponse> response = apiInstance.deleteS3ConfigWithHttpInfo();
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling IntegrationsApi#deleteS3Config");
            System.err.println("Status code: " + e.getCode());
            System.err.println("Response headers: " + e.getResponseHeaders());
            System.err.println("Reason: " + e.getResponseBody());
            e.printStackTrace();
        }
    }
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

ApiResponse<[**S3SuccessResponse**](S3SuccessResponse.md)>


### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Configuration deleted successfully |  -  |
| **403** | Admin privileges required |  -  |
| **422** | Validation Error |  -  |


## getS3Config

> S3ConfigResponse getS3Config()

Get S3 configuration

Get current S3 storage configuration.  **Authentication:** API Key required (&#x60;x-api-key&#x60; header) with admin privileges  **Usage:** Retrieve your S3 integration settings. Secret access key is masked for security.  **Returns 404** if S3 is not configured.  **No credits consumed:** This is a read-only endpoint.

### Example

```java
// Import classes:
import com.templatefox.sdk.ApiClient;
import com.templatefox.sdk.ApiException;
import com.templatefox.sdk.Configuration;
import com.templatefox.sdk.auth.*;
import com.templatefox.sdk.models.*;
import com.templatefox.sdk.api.IntegrationsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.pdftemplateapi.com");
        
        // Configure API key authorization: ApiKeyAuth
        ApiKeyAuth ApiKeyAuth = (ApiKeyAuth) defaultClient.getAuthentication("ApiKeyAuth");
        ApiKeyAuth.setApiKey("YOUR API KEY");
        // Uncomment the following line to set a prefix for the API key, e.g. "Token" (defaults to null)
        //ApiKeyAuth.setApiKeyPrefix("Token");

        IntegrationsApi apiInstance = new IntegrationsApi(defaultClient);
        try {
            S3ConfigResponse result = apiInstance.getS3Config();
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling IntegrationsApi#getS3Config");
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

[**S3ConfigResponse**](S3ConfigResponse.md)


### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | S3 configuration retrieved successfully |  -  |
| **403** | Admin privileges required |  -  |
| **404** | S3 is not configured |  -  |
| **422** | Validation Error |  -  |

## getS3ConfigWithHttpInfo

> ApiResponse<S3ConfigResponse> getS3Config getS3ConfigWithHttpInfo()

Get S3 configuration

Get current S3 storage configuration.  **Authentication:** API Key required (&#x60;x-api-key&#x60; header) with admin privileges  **Usage:** Retrieve your S3 integration settings. Secret access key is masked for security.  **Returns 404** if S3 is not configured.  **No credits consumed:** This is a read-only endpoint.

### Example

```java
// Import classes:
import com.templatefox.sdk.ApiClient;
import com.templatefox.sdk.ApiException;
import com.templatefox.sdk.ApiResponse;
import com.templatefox.sdk.Configuration;
import com.templatefox.sdk.auth.*;
import com.templatefox.sdk.models.*;
import com.templatefox.sdk.api.IntegrationsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.pdftemplateapi.com");
        
        // Configure API key authorization: ApiKeyAuth
        ApiKeyAuth ApiKeyAuth = (ApiKeyAuth) defaultClient.getAuthentication("ApiKeyAuth");
        ApiKeyAuth.setApiKey("YOUR API KEY");
        // Uncomment the following line to set a prefix for the API key, e.g. "Token" (defaults to null)
        //ApiKeyAuth.setApiKeyPrefix("Token");

        IntegrationsApi apiInstance = new IntegrationsApi(defaultClient);
        try {
            ApiResponse<S3ConfigResponse> response = apiInstance.getS3ConfigWithHttpInfo();
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling IntegrationsApi#getS3Config");
            System.err.println("Status code: " + e.getCode());
            System.err.println("Response headers: " + e.getResponseHeaders());
            System.err.println("Reason: " + e.getResponseBody());
            e.printStackTrace();
        }
    }
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

ApiResponse<[**S3ConfigResponse**](S3ConfigResponse.md)>


### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | S3 configuration retrieved successfully |  -  |
| **403** | Admin privileges required |  -  |
| **404** | S3 is not configured |  -  |
| **422** | Validation Error |  -  |


## saveS3Config

> S3SuccessResponse saveS3Config(s3ConfigRequest)

Save S3 configuration

Save or update S3-compatible storage configuration.  **Authentication:** API Key required (&#x60;x-api-key&#x60; header) with admin privileges  **Usage:** Configure your S3-compatible storage to receive generated PDFs directly in your own bucket instead of the default CDN.  **Supported providers:** - Amazon S3 - DigitalOcean Spaces - Cloudflare R2 - MinIO - Any S3-compatible storage  **Secret key behavior:** - For new configuration: &#x60;secret_access_key&#x60; is required - For updates: Omit &#x60;secret_access_key&#x60; to keep existing value  **No credits consumed:** This is a configuration endpoint.

### Example

```java
// Import classes:
import com.templatefox.sdk.ApiClient;
import com.templatefox.sdk.ApiException;
import com.templatefox.sdk.Configuration;
import com.templatefox.sdk.auth.*;
import com.templatefox.sdk.models.*;
import com.templatefox.sdk.api.IntegrationsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.pdftemplateapi.com");
        
        // Configure API key authorization: ApiKeyAuth
        ApiKeyAuth ApiKeyAuth = (ApiKeyAuth) defaultClient.getAuthentication("ApiKeyAuth");
        ApiKeyAuth.setApiKey("YOUR API KEY");
        // Uncomment the following line to set a prefix for the API key, e.g. "Token" (defaults to null)
        //ApiKeyAuth.setApiKeyPrefix("Token");

        IntegrationsApi apiInstance = new IntegrationsApi(defaultClient);
        S3ConfigRequest s3ConfigRequest = new S3ConfigRequest(); // S3ConfigRequest | 
        try {
            S3SuccessResponse result = apiInstance.saveS3Config(s3ConfigRequest);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling IntegrationsApi#saveS3Config");
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
| **s3ConfigRequest** | [**S3ConfigRequest**](S3ConfigRequest.md)|  | |

### Return type

[**S3SuccessResponse**](S3SuccessResponse.md)


### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Configuration saved successfully |  -  |
| **400** | Invalid configuration (e.g., missing secret key for new config) |  -  |
| **403** | Admin privileges required |  -  |
| **422** | Validation Error |  -  |

## saveS3ConfigWithHttpInfo

> ApiResponse<S3SuccessResponse> saveS3Config saveS3ConfigWithHttpInfo(s3ConfigRequest)

Save S3 configuration

Save or update S3-compatible storage configuration.  **Authentication:** API Key required (&#x60;x-api-key&#x60; header) with admin privileges  **Usage:** Configure your S3-compatible storage to receive generated PDFs directly in your own bucket instead of the default CDN.  **Supported providers:** - Amazon S3 - DigitalOcean Spaces - Cloudflare R2 - MinIO - Any S3-compatible storage  **Secret key behavior:** - For new configuration: &#x60;secret_access_key&#x60; is required - For updates: Omit &#x60;secret_access_key&#x60; to keep existing value  **No credits consumed:** This is a configuration endpoint.

### Example

```java
// Import classes:
import com.templatefox.sdk.ApiClient;
import com.templatefox.sdk.ApiException;
import com.templatefox.sdk.ApiResponse;
import com.templatefox.sdk.Configuration;
import com.templatefox.sdk.auth.*;
import com.templatefox.sdk.models.*;
import com.templatefox.sdk.api.IntegrationsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.pdftemplateapi.com");
        
        // Configure API key authorization: ApiKeyAuth
        ApiKeyAuth ApiKeyAuth = (ApiKeyAuth) defaultClient.getAuthentication("ApiKeyAuth");
        ApiKeyAuth.setApiKey("YOUR API KEY");
        // Uncomment the following line to set a prefix for the API key, e.g. "Token" (defaults to null)
        //ApiKeyAuth.setApiKeyPrefix("Token");

        IntegrationsApi apiInstance = new IntegrationsApi(defaultClient);
        S3ConfigRequest s3ConfigRequest = new S3ConfigRequest(); // S3ConfigRequest | 
        try {
            ApiResponse<S3SuccessResponse> response = apiInstance.saveS3ConfigWithHttpInfo(s3ConfigRequest);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling IntegrationsApi#saveS3Config");
            System.err.println("Status code: " + e.getCode());
            System.err.println("Response headers: " + e.getResponseHeaders());
            System.err.println("Reason: " + e.getResponseBody());
            e.printStackTrace();
        }
    }
}
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **s3ConfigRequest** | [**S3ConfigRequest**](S3ConfigRequest.md)|  | |

### Return type

ApiResponse<[**S3SuccessResponse**](S3SuccessResponse.md)>


### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Configuration saved successfully |  -  |
| **400** | Invalid configuration (e.g., missing secret key for new config) |  -  |
| **403** | Admin privileges required |  -  |
| **422** | Validation Error |  -  |


## testS3Connection

> S3TestResponse testS3Connection()

Test S3 connection

Test S3 connection with stored credentials.  **Authentication:** API Key required (&#x60;x-api-key&#x60; header) with admin privileges  **Usage:** Verify your S3 configuration is working correctly. The test will: 1. Connect to the endpoint 2. Verify bucket access 3. Check write permissions by uploading a small test file  **Prerequisite:** S3 must be configured first using &#x60;POST /v1/integrations/s3&#x60;  **No credits consumed:** This is a diagnostic endpoint.

### Example

```java
// Import classes:
import com.templatefox.sdk.ApiClient;
import com.templatefox.sdk.ApiException;
import com.templatefox.sdk.Configuration;
import com.templatefox.sdk.auth.*;
import com.templatefox.sdk.models.*;
import com.templatefox.sdk.api.IntegrationsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.pdftemplateapi.com");
        
        // Configure API key authorization: ApiKeyAuth
        ApiKeyAuth ApiKeyAuth = (ApiKeyAuth) defaultClient.getAuthentication("ApiKeyAuth");
        ApiKeyAuth.setApiKey("YOUR API KEY");
        // Uncomment the following line to set a prefix for the API key, e.g. "Token" (defaults to null)
        //ApiKeyAuth.setApiKeyPrefix("Token");

        IntegrationsApi apiInstance = new IntegrationsApi(defaultClient);
        try {
            S3TestResponse result = apiInstance.testS3Connection();
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling IntegrationsApi#testS3Connection");
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

[**S3TestResponse**](S3TestResponse.md)


### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Connection test successful |  -  |
| **400** | Connection test failed |  -  |
| **403** | Admin privileges required |  -  |
| **422** | Validation Error |  -  |

## testS3ConnectionWithHttpInfo

> ApiResponse<S3TestResponse> testS3Connection testS3ConnectionWithHttpInfo()

Test S3 connection

Test S3 connection with stored credentials.  **Authentication:** API Key required (&#x60;x-api-key&#x60; header) with admin privileges  **Usage:** Verify your S3 configuration is working correctly. The test will: 1. Connect to the endpoint 2. Verify bucket access 3. Check write permissions by uploading a small test file  **Prerequisite:** S3 must be configured first using &#x60;POST /v1/integrations/s3&#x60;  **No credits consumed:** This is a diagnostic endpoint.

### Example

```java
// Import classes:
import com.templatefox.sdk.ApiClient;
import com.templatefox.sdk.ApiException;
import com.templatefox.sdk.ApiResponse;
import com.templatefox.sdk.Configuration;
import com.templatefox.sdk.auth.*;
import com.templatefox.sdk.models.*;
import com.templatefox.sdk.api.IntegrationsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.pdftemplateapi.com");
        
        // Configure API key authorization: ApiKeyAuth
        ApiKeyAuth ApiKeyAuth = (ApiKeyAuth) defaultClient.getAuthentication("ApiKeyAuth");
        ApiKeyAuth.setApiKey("YOUR API KEY");
        // Uncomment the following line to set a prefix for the API key, e.g. "Token" (defaults to null)
        //ApiKeyAuth.setApiKeyPrefix("Token");

        IntegrationsApi apiInstance = new IntegrationsApi(defaultClient);
        try {
            ApiResponse<S3TestResponse> response = apiInstance.testS3ConnectionWithHttpInfo();
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling IntegrationsApi#testS3Connection");
            System.err.println("Status code: " + e.getCode());
            System.err.println("Response headers: " + e.getResponseHeaders());
            System.err.println("Reason: " + e.getResponseBody());
            e.printStackTrace();
        }
    }
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

ApiResponse<[**S3TestResponse**](S3TestResponse.md)>


### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Connection test successful |  -  |
| **400** | Connection test failed |  -  |
| **403** | Admin privileges required |  -  |
| **422** | Validation Error |  -  |

