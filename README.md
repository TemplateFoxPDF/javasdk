# TemplateFox Java SDK

Official Java SDK for [TemplateFox](https://pdftemplateapi.com) - Generate PDFs from HTML templates via API.

[![Maven Central](https://maven-badges.herokuapp.com/maven-central/io.github.templatefoxpdf/sdk/badge.svg)](https://maven-badges.herokuapp.com/maven-central/io.github.templatefoxpdf/sdk)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## Installation

### Maven

```xml
<dependency>
    <groupId>io.github.templatefoxpdf</groupId>
    <artifactId>sdk</artifactId>
    <version>1.0.0</version>
</dependency>
```

### Gradle

```groovy
implementation 'io.github.templatefoxpdf:sdk:1.0.0'
```

## Quick Start

```java
import com.templatefox.sdk.ApiClient;
import com.templatefox.sdk.api.PDFApi;
import com.templatefox.sdk.model.CreatePdfRequest;

public class Example {
    public static void main(String[] args) {
        // Initialize the client
        ApiClient client = new ApiClient();
        client.setApiKey("your-api-key");

        PDFApi api = new PDFApi(client);

        // Generate a PDF
        CreatePdfRequest request = new CreatePdfRequest()
            .templateId("YOUR_TEMPLATE_ID")
            .putDataItem("name", "John Doe")
            .putDataItem("invoice_number", "INV-001")
            .putDataItem("total_amount", 150.00);

        try {
            var response = api.createPdf(request);
            System.out.println("PDF URL: " + response.getUrl());
            System.out.println("Credits remaining: " + response.getCreditsRemaining());
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

## Features

- **Template-based PDF generation** - Create templates with dynamic variables, generate PDFs with your data
- **Multiple export options** - Get a signed URL (default) or raw binary PDF
- **S3 integration** - Upload generated PDFs directly to your own S3-compatible storage
- **Java 8+** - Compatible with Java 8 and above

## API Methods

### PDF Generation

```java
CreatePdfRequest request = new CreatePdfRequest()
    .templateId("TEMPLATE_ID")
    .putDataItem("name", "John Doe")
    .exportType(ExportType.URL)     // URL or BINARY
    .expiration(86400)               // URL expiration in seconds
    .filename("invoice-001");        // Custom filename

var response = api.createPdf(request);
```

### Templates

```java
import com.templatefox.sdk.api.TemplatesApi;

TemplatesApi templatesApi = new TemplatesApi(client);

// List all templates
var templates = templatesApi.listTemplates();
for (var template : templates.getTemplates()) {
    System.out.println(template.getId() + ": " + template.getName());
}

// Get template fields
var fields = templatesApi.getTemplateFields("TEMPLATE_ID");
for (var field : fields) {
    System.out.println(field.getKey() + ": " + field.getType());
}
```

### Account

```java
import com.templatefox.sdk.api.AccountApi;

AccountApi accountApi = new AccountApi(client);

// Get account info
var account = accountApi.getAccount();
System.out.println("Credits: " + account.getCredits());
System.out.println("Email: " + account.getEmail());

// List transactions
var transactions = accountApi.listTransactions(100, 0);
for (var tx : transactions.getTransactions()) {
    System.out.println(tx.getTransactionType() + ": " + tx.getCredits());
}
```

### S3 Integration

```java
import com.templatefox.sdk.api.IntegrationsApi;

IntegrationsApi integrationsApi = new IntegrationsApi(client);

// Save S3 configuration
S3ConfigRequest s3Config = new S3ConfigRequest()
    .endpointUrl("https://s3.amazonaws.com")
    .accessKeyId("AKIAIOSFODNN7EXAMPLE")
    .secretAccessKey("your-secret-key")
    .bucketName("my-pdf-bucket")
    .defaultPrefix("generated/pdfs/");

integrationsApi.saveS3Config(s3Config);

// Test connection
var test = integrationsApi.testS3Connection();
System.out.println("Connection: " + (test.getSuccess() ? "OK" : "Failed"));
```

## Configuration

```java
ApiClient client = new ApiClient();
client.setBasePath("https://api.pdftemplateapi.com");  // Default API URL
client.setApiKey("your-api-key");

// Or use environment variable
client.setApiKey(System.getenv("TEMPLATEFOX_API_KEY"));
```

## Error Handling

```java
import com.templatefox.sdk.ApiException;

try {
    var response = api.createPdf(request);
} catch (ApiException e) {
    switch (e.getCode()) {
        case 402:
            System.err.println("Insufficient credits");
            break;
        case 403:
            System.err.println("Access denied - check your API key");
            break;
        case 404:
            System.err.println("Template not found");
            break;
        default:
            System.err.println("Error: " + e.getMessage());
    }
}
```

## Documentation

- [API Documentation](https://pdftemplateapi.com/docs)
- [Swagger UI](https://api.pdftemplateapi.com/docs)
- [Dashboard](https://pdftemplateapi.com/dashboard)

## Support

- Email: support@pdftemplateapi.com
- Issues: [GitHub Issues](https://github.com/TemplateFoxPDF/javasdk/issues)

## License

MIT License - see [LICENSE](LICENSE) for details.
