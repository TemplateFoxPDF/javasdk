# PdfApi

All URIs are relative to *https://api.pdftemplateapi.com*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createPdf**](PdfApi.md#createPdf) | **POST** /v1/pdf/create | Generate PDF from template |
| [**createPdfWithHttpInfo**](PdfApi.md#createPdfWithHttpInfo) | **POST** /v1/pdf/create | Generate PDF from template |



## createPdf

> CreatePdfResponse createPdf(createPdfRequest)

Generate PDF from template

Generate a PDF from a saved template with dynamic data.  **Authentication:** API Key required (&#x60;x-api-key&#x60; header)  ## Request Body  | Field | Type | Required | Description | |-------|------|----------|-------------| | &#x60;template_id&#x60; | string | ✅ Yes | Template short ID (12 characters) | | &#x60;data&#x60; | object | ✅ Yes | Key-value data to render in template | | &#x60;export_type&#x60; | string | No | &#x60;url&#x60; (default) or &#x60;binary&#x60; | | &#x60;expiration&#x60; | integer | No | URL expiration in seconds (60-604800, default: 86400) |  ## Export Types - &#x60;url&#x60; (default): PDF is uploaded to CDN, returns JSON with URL - &#x60;binary&#x60;: Returns raw PDF bytes directly  **Credits:** 1 credit deducted per successful generation.

### Example

```java
// Import classes:
import com.templatefox.sdk.ApiClient;
import com.templatefox.sdk.ApiException;
import com.templatefox.sdk.Configuration;
import com.templatefox.sdk.auth.*;
import com.templatefox.sdk.models.*;
import com.templatefox.sdk.api.PdfApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.pdftemplateapi.com");
        
        // Configure API key authorization: ApiKeyAuth
        ApiKeyAuth ApiKeyAuth = (ApiKeyAuth) defaultClient.getAuthentication("ApiKeyAuth");
        ApiKeyAuth.setApiKey("YOUR API KEY");
        // Uncomment the following line to set a prefix for the API key, e.g. "Token" (defaults to null)
        //ApiKeyAuth.setApiKeyPrefix("Token");

        PdfApi apiInstance = new PdfApi(defaultClient);
        CreatePdfRequest createPdfRequest = new CreatePdfRequest(); // CreatePdfRequest | 
        try {
            CreatePdfResponse result = apiInstance.createPdf(createPdfRequest);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling PdfApi#createPdf");
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
| **createPdfRequest** | [**CreatePdfRequest**](CreatePdfRequest.md)|  | |

### Return type

[**CreatePdfResponse**](CreatePdfResponse.md)


### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/pdf

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | PDF generated successfully |  -  |
| **402** | Insufficient credits |  -  |
| **403** | Access denied - not your template |  -  |
| **404** | Template not found |  -  |
| **422** | Validation Error |  -  |

## createPdfWithHttpInfo

> ApiResponse<CreatePdfResponse> createPdf createPdfWithHttpInfo(createPdfRequest)

Generate PDF from template

Generate a PDF from a saved template with dynamic data.  **Authentication:** API Key required (&#x60;x-api-key&#x60; header)  ## Request Body  | Field | Type | Required | Description | |-------|------|----------|-------------| | &#x60;template_id&#x60; | string | ✅ Yes | Template short ID (12 characters) | | &#x60;data&#x60; | object | ✅ Yes | Key-value data to render in template | | &#x60;export_type&#x60; | string | No | &#x60;url&#x60; (default) or &#x60;binary&#x60; | | &#x60;expiration&#x60; | integer | No | URL expiration in seconds (60-604800, default: 86400) |  ## Export Types - &#x60;url&#x60; (default): PDF is uploaded to CDN, returns JSON with URL - &#x60;binary&#x60;: Returns raw PDF bytes directly  **Credits:** 1 credit deducted per successful generation.

### Example

```java
// Import classes:
import com.templatefox.sdk.ApiClient;
import com.templatefox.sdk.ApiException;
import com.templatefox.sdk.ApiResponse;
import com.templatefox.sdk.Configuration;
import com.templatefox.sdk.auth.*;
import com.templatefox.sdk.models.*;
import com.templatefox.sdk.api.PdfApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.pdftemplateapi.com");
        
        // Configure API key authorization: ApiKeyAuth
        ApiKeyAuth ApiKeyAuth = (ApiKeyAuth) defaultClient.getAuthentication("ApiKeyAuth");
        ApiKeyAuth.setApiKey("YOUR API KEY");
        // Uncomment the following line to set a prefix for the API key, e.g. "Token" (defaults to null)
        //ApiKeyAuth.setApiKeyPrefix("Token");

        PdfApi apiInstance = new PdfApi(defaultClient);
        CreatePdfRequest createPdfRequest = new CreatePdfRequest(); // CreatePdfRequest | 
        try {
            ApiResponse<CreatePdfResponse> response = apiInstance.createPdfWithHttpInfo(createPdfRequest);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling PdfApi#createPdf");
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
| **createPdfRequest** | [**CreatePdfRequest**](CreatePdfRequest.md)|  | |

### Return type

ApiResponse<[**CreatePdfResponse**](CreatePdfResponse.md)>


### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/pdf

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | PDF generated successfully |  -  |
| **402** | Insufficient credits |  -  |
| **403** | Access denied - not your template |  -  |
| **404** | Template not found |  -  |
| **422** | Validation Error |  -  |

