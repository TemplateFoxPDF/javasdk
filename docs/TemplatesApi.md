# TemplatesApi

All URIs are relative to *https://api.pdftemplateapi.com*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**getTemplateFields**](TemplatesApi.md#getTemplateFields) | **GET** /v1/templates/{template_id}/fields | Get template fields |
| [**getTemplateFieldsWithHttpInfo**](TemplatesApi.md#getTemplateFieldsWithHttpInfo) | **GET** /v1/templates/{template_id}/fields | Get template fields |
| [**listTemplates**](TemplatesApi.md#listTemplates) | **GET** /v1/templates | List templates |
| [**listTemplatesWithHttpInfo**](TemplatesApi.md#listTemplatesWithHttpInfo) | **GET** /v1/templates | List templates |



## getTemplateFields

> List<TemplateField> getTemplateFields(templateId)

Get template fields

Get the dynamic fields for a template.  **Authentication:** API Key required (&#x60;x-api-key&#x60; header) or JWT token  **Usage:** This endpoint is designed for Zapier Dynamic Fields integration. It returns an array of field definitions that Zapier uses to dynamically generate input forms.  **Response format:** Array of objects compatible with Zapier InputFieldsSchema. Each field has: &#x60;key&#x60;, &#x60;label&#x60;, &#x60;type&#x60;, &#x60;required&#x60;, and optional &#x60;helpText&#x60;.  **Field types:** - &#x60;string&#x60;: Text input (also used for JSON arrays/objects) - &#x60;integer&#x60;: Integer number - &#x60;number&#x60;: Decimal number - &#x60;boolean&#x60;: True/False checkbox  **Arrays and objects:** Complex types are returned as &#x60;string&#x60; type with a &#x60;helpText&#x60; showing the expected JSON format.  **No credits consumed:** This is a read-only endpoint.

### Example

```java
// Import classes:
import com.templatefox.sdk.ApiClient;
import com.templatefox.sdk.ApiException;
import com.templatefox.sdk.Configuration;
import com.templatefox.sdk.auth.*;
import com.templatefox.sdk.models.*;
import com.templatefox.sdk.api.TemplatesApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.pdftemplateapi.com");
        
        // Configure API key authorization: ApiKeyAuth
        ApiKeyAuth ApiKeyAuth = (ApiKeyAuth) defaultClient.getAuthentication("ApiKeyAuth");
        ApiKeyAuth.setApiKey("YOUR API KEY");
        // Uncomment the following line to set a prefix for the API key, e.g. "Token" (defaults to null)
        //ApiKeyAuth.setApiKeyPrefix("Token");

        TemplatesApi apiInstance = new TemplatesApi(defaultClient);
        String templateId = "templateId_example"; // String | 
        try {
            List<TemplateField> result = apiInstance.getTemplateFields(templateId);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling TemplatesApi#getTemplateFields");
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
| **templateId** | **String**|  | |

### Return type

[**List&lt;TemplateField&gt;**](TemplateField.md)


### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List of template fields |  -  |
| **403** | Invalid or missing API key |  -  |
| **404** | Template not found |  -  |
| **422** | Validation Error |  -  |

## getTemplateFieldsWithHttpInfo

> ApiResponse<List<TemplateField>> getTemplateFields getTemplateFieldsWithHttpInfo(templateId)

Get template fields

Get the dynamic fields for a template.  **Authentication:** API Key required (&#x60;x-api-key&#x60; header) or JWT token  **Usage:** This endpoint is designed for Zapier Dynamic Fields integration. It returns an array of field definitions that Zapier uses to dynamically generate input forms.  **Response format:** Array of objects compatible with Zapier InputFieldsSchema. Each field has: &#x60;key&#x60;, &#x60;label&#x60;, &#x60;type&#x60;, &#x60;required&#x60;, and optional &#x60;helpText&#x60;.  **Field types:** - &#x60;string&#x60;: Text input (also used for JSON arrays/objects) - &#x60;integer&#x60;: Integer number - &#x60;number&#x60;: Decimal number - &#x60;boolean&#x60;: True/False checkbox  **Arrays and objects:** Complex types are returned as &#x60;string&#x60; type with a &#x60;helpText&#x60; showing the expected JSON format.  **No credits consumed:** This is a read-only endpoint.

### Example

```java
// Import classes:
import com.templatefox.sdk.ApiClient;
import com.templatefox.sdk.ApiException;
import com.templatefox.sdk.ApiResponse;
import com.templatefox.sdk.Configuration;
import com.templatefox.sdk.auth.*;
import com.templatefox.sdk.models.*;
import com.templatefox.sdk.api.TemplatesApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.pdftemplateapi.com");
        
        // Configure API key authorization: ApiKeyAuth
        ApiKeyAuth ApiKeyAuth = (ApiKeyAuth) defaultClient.getAuthentication("ApiKeyAuth");
        ApiKeyAuth.setApiKey("YOUR API KEY");
        // Uncomment the following line to set a prefix for the API key, e.g. "Token" (defaults to null)
        //ApiKeyAuth.setApiKeyPrefix("Token");

        TemplatesApi apiInstance = new TemplatesApi(defaultClient);
        String templateId = "templateId_example"; // String | 
        try {
            ApiResponse<List<TemplateField>> response = apiInstance.getTemplateFieldsWithHttpInfo(templateId);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling TemplatesApi#getTemplateFields");
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
| **templateId** | **String**|  | |

### Return type

ApiResponse<[**List&lt;TemplateField&gt;**](TemplateField.md)>


### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List of template fields |  -  |
| **403** | Invalid or missing API key |  -  |
| **404** | Template not found |  -  |
| **422** | Validation Error |  -  |


## listTemplates

> TemplatesListResponse listTemplates()

List templates

List all templates for the authenticated user.  **Authentication:** API Key required (&#x60;x-api-key&#x60; header) or JWT token  **Usage:** This endpoint is designed for no-code tools (Zapier, Make, n8n) to populate template selection dropdowns.  **No credits consumed:** This is a read-only endpoint.

### Example

```java
// Import classes:
import com.templatefox.sdk.ApiClient;
import com.templatefox.sdk.ApiException;
import com.templatefox.sdk.Configuration;
import com.templatefox.sdk.auth.*;
import com.templatefox.sdk.models.*;
import com.templatefox.sdk.api.TemplatesApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.pdftemplateapi.com");
        
        // Configure API key authorization: ApiKeyAuth
        ApiKeyAuth ApiKeyAuth = (ApiKeyAuth) defaultClient.getAuthentication("ApiKeyAuth");
        ApiKeyAuth.setApiKey("YOUR API KEY");
        // Uncomment the following line to set a prefix for the API key, e.g. "Token" (defaults to null)
        //ApiKeyAuth.setApiKeyPrefix("Token");

        TemplatesApi apiInstance = new TemplatesApi(defaultClient);
        try {
            TemplatesListResponse result = apiInstance.listTemplates();
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling TemplatesApi#listTemplates");
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

[**TemplatesListResponse**](TemplatesListResponse.md)


### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List of templates |  -  |
| **403** | Invalid or missing API key |  -  |
| **422** | Validation Error |  -  |

## listTemplatesWithHttpInfo

> ApiResponse<TemplatesListResponse> listTemplates listTemplatesWithHttpInfo()

List templates

List all templates for the authenticated user.  **Authentication:** API Key required (&#x60;x-api-key&#x60; header) or JWT token  **Usage:** This endpoint is designed for no-code tools (Zapier, Make, n8n) to populate template selection dropdowns.  **No credits consumed:** This is a read-only endpoint.

### Example

```java
// Import classes:
import com.templatefox.sdk.ApiClient;
import com.templatefox.sdk.ApiException;
import com.templatefox.sdk.ApiResponse;
import com.templatefox.sdk.Configuration;
import com.templatefox.sdk.auth.*;
import com.templatefox.sdk.models.*;
import com.templatefox.sdk.api.TemplatesApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.pdftemplateapi.com");
        
        // Configure API key authorization: ApiKeyAuth
        ApiKeyAuth ApiKeyAuth = (ApiKeyAuth) defaultClient.getAuthentication("ApiKeyAuth");
        ApiKeyAuth.setApiKey("YOUR API KEY");
        // Uncomment the following line to set a prefix for the API key, e.g. "Token" (defaults to null)
        //ApiKeyAuth.setApiKeyPrefix("Token");

        TemplatesApi apiInstance = new TemplatesApi(defaultClient);
        try {
            ApiResponse<TemplatesListResponse> response = apiInstance.listTemplatesWithHttpInfo();
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling TemplatesApi#listTemplates");
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

ApiResponse<[**TemplatesListResponse**](TemplatesListResponse.md)>


### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List of templates |  -  |
| **403** | Invalid or missing API key |  -  |
| **422** | Validation Error |  -  |

