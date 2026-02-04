# AccountApi

All URIs are relative to *https://api.pdftemplateapi.com*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**getAccount**](AccountApi.md#getAccount) | **GET** /v1/account | Get account info |
| [**getAccountWithHttpInfo**](AccountApi.md#getAccountWithHttpInfo) | **GET** /v1/account | Get account info |
| [**listTransactions**](AccountApi.md#listTransactions) | **GET** /v1/account/transactions | List transactions |
| [**listTransactionsWithHttpInfo**](AccountApi.md#listTransactionsWithHttpInfo) | **GET** /v1/account/transactions | List transactions |



## getAccount

> AccountInfoResponse getAccount()

Get account info

Get account information including remaining credits.  **Authentication:** API Key required (&#x60;x-api-key&#x60; header) or JWT token  **Usage:** Check credit balance before performing operations.  **No credits consumed:** This is a read-only endpoint.

### Example

```java
// Import classes:
import com.templatefox.sdk.ApiClient;
import com.templatefox.sdk.ApiException;
import com.templatefox.sdk.Configuration;
import com.templatefox.sdk.auth.*;
import com.templatefox.sdk.models.*;
import com.templatefox.sdk.api.AccountApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.pdftemplateapi.com");
        
        // Configure API key authorization: ApiKeyAuth
        ApiKeyAuth ApiKeyAuth = (ApiKeyAuth) defaultClient.getAuthentication("ApiKeyAuth");
        ApiKeyAuth.setApiKey("YOUR API KEY");
        // Uncomment the following line to set a prefix for the API key, e.g. "Token" (defaults to null)
        //ApiKeyAuth.setApiKeyPrefix("Token");

        AccountApi apiInstance = new AccountApi(defaultClient);
        try {
            AccountInfoResponse result = apiInstance.getAccount();
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling AccountApi#getAccount");
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

[**AccountInfoResponse**](AccountInfoResponse.md)


### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Account information |  -  |
| **403** | Invalid or missing API key |  -  |
| **422** | Validation Error |  -  |

## getAccountWithHttpInfo

> ApiResponse<AccountInfoResponse> getAccount getAccountWithHttpInfo()

Get account info

Get account information including remaining credits.  **Authentication:** API Key required (&#x60;x-api-key&#x60; header) or JWT token  **Usage:** Check credit balance before performing operations.  **No credits consumed:** This is a read-only endpoint.

### Example

```java
// Import classes:
import com.templatefox.sdk.ApiClient;
import com.templatefox.sdk.ApiException;
import com.templatefox.sdk.ApiResponse;
import com.templatefox.sdk.Configuration;
import com.templatefox.sdk.auth.*;
import com.templatefox.sdk.models.*;
import com.templatefox.sdk.api.AccountApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.pdftemplateapi.com");
        
        // Configure API key authorization: ApiKeyAuth
        ApiKeyAuth ApiKeyAuth = (ApiKeyAuth) defaultClient.getAuthentication("ApiKeyAuth");
        ApiKeyAuth.setApiKey("YOUR API KEY");
        // Uncomment the following line to set a prefix for the API key, e.g. "Token" (defaults to null)
        //ApiKeyAuth.setApiKeyPrefix("Token");

        AccountApi apiInstance = new AccountApi(defaultClient);
        try {
            ApiResponse<AccountInfoResponse> response = apiInstance.getAccountWithHttpInfo();
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling AccountApi#getAccount");
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

ApiResponse<[**AccountInfoResponse**](AccountInfoResponse.md)>


### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Account information |  -  |
| **403** | Invalid or missing API key |  -  |
| **422** | Validation Error |  -  |


## listTransactions

> TransactionsResponse listTransactions(limit, offset)

List transactions

List transaction history for the authenticated user.  **Authentication:** API Key required (&#x60;x-api-key&#x60; header) or JWT token  **Pagination:** Use &#x60;limit&#x60; and &#x60;offset&#x60; query parameters.  **Transaction types:** - &#x60;PDFGEN&#x60;: PDF generation (consumes credits) - &#x60;REFUND&#x60;: Credit refund (on failed generation) - &#x60;PURCHASE&#x60;: Credit purchase - &#x60;BONUS&#x60;: Bonus credits  **Credits field:** - Positive value &#x3D; credits consumed - Negative value &#x3D; credits added  **No credits consumed:** This is a read-only endpoint.

### Example

```java
// Import classes:
import com.templatefox.sdk.ApiClient;
import com.templatefox.sdk.ApiException;
import com.templatefox.sdk.Configuration;
import com.templatefox.sdk.auth.*;
import com.templatefox.sdk.models.*;
import com.templatefox.sdk.api.AccountApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.pdftemplateapi.com");
        
        // Configure API key authorization: ApiKeyAuth
        ApiKeyAuth ApiKeyAuth = (ApiKeyAuth) defaultClient.getAuthentication("ApiKeyAuth");
        ApiKeyAuth.setApiKey("YOUR API KEY");
        // Uncomment the following line to set a prefix for the API key, e.g. "Token" (defaults to null)
        //ApiKeyAuth.setApiKeyPrefix("Token");

        AccountApi apiInstance = new AccountApi(defaultClient);
        Integer limit = 300; // Integer | Number of records to return
        Integer offset = 0; // Integer | Number of records to skip
        try {
            TransactionsResponse result = apiInstance.listTransactions(limit, offset);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling AccountApi#listTransactions");
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
| **limit** | **Integer**| Number of records to return | [optional] [default to 300] |
| **offset** | **Integer**| Number of records to skip | [optional] [default to 0] |

### Return type

[**TransactionsResponse**](TransactionsResponse.md)


### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Transaction history |  -  |
| **403** | Invalid or missing API key |  -  |
| **422** | Validation Error |  -  |

## listTransactionsWithHttpInfo

> ApiResponse<TransactionsResponse> listTransactions listTransactionsWithHttpInfo(limit, offset)

List transactions

List transaction history for the authenticated user.  **Authentication:** API Key required (&#x60;x-api-key&#x60; header) or JWT token  **Pagination:** Use &#x60;limit&#x60; and &#x60;offset&#x60; query parameters.  **Transaction types:** - &#x60;PDFGEN&#x60;: PDF generation (consumes credits) - &#x60;REFUND&#x60;: Credit refund (on failed generation) - &#x60;PURCHASE&#x60;: Credit purchase - &#x60;BONUS&#x60;: Bonus credits  **Credits field:** - Positive value &#x3D; credits consumed - Negative value &#x3D; credits added  **No credits consumed:** This is a read-only endpoint.

### Example

```java
// Import classes:
import com.templatefox.sdk.ApiClient;
import com.templatefox.sdk.ApiException;
import com.templatefox.sdk.ApiResponse;
import com.templatefox.sdk.Configuration;
import com.templatefox.sdk.auth.*;
import com.templatefox.sdk.models.*;
import com.templatefox.sdk.api.AccountApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.pdftemplateapi.com");
        
        // Configure API key authorization: ApiKeyAuth
        ApiKeyAuth ApiKeyAuth = (ApiKeyAuth) defaultClient.getAuthentication("ApiKeyAuth");
        ApiKeyAuth.setApiKey("YOUR API KEY");
        // Uncomment the following line to set a prefix for the API key, e.g. "Token" (defaults to null)
        //ApiKeyAuth.setApiKeyPrefix("Token");

        AccountApi apiInstance = new AccountApi(defaultClient);
        Integer limit = 300; // Integer | Number of records to return
        Integer offset = 0; // Integer | Number of records to skip
        try {
            ApiResponse<TransactionsResponse> response = apiInstance.listTransactionsWithHttpInfo(limit, offset);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling AccountApi#listTransactions");
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
| **limit** | **Integer**| Number of records to return | [optional] [default to 300] |
| **offset** | **Integer**| Number of records to skip | [optional] [default to 0] |

### Return type

ApiResponse<[**TransactionsResponse**](TransactionsResponse.md)>


### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Transaction history |  -  |
| **403** | Invalid or missing API key |  -  |
| **422** | Validation Error |  -  |

