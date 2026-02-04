

# CreatePdfRequest

Request model for PDF generation

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**templateId** | **String** | **Required.** Template short ID (12 characters) |  |
|**data** | **Map&lt;String, Object&gt;** | **Required.** Key-value data to render in the template. Keys must match template variables. |  |
|**exportType** | **ExportType** | Export format: &#x60;url&#x60; uploads to CDN and returns URL, &#x60;binary&#x60; returns raw PDF bytes |  [optional] |
|**expiration** | **Integer** | URL expiration in seconds. Min: 60 (1 min), Max: 604800 (7 days). Only applies to &#x60;url&#x60; export type. |  [optional] |
|**filename** | **String** |  |  [optional] |
|**storeS3** | **Boolean** | Upload to your configured S3 bucket instead of CDN |  [optional] |
|**s3Filepath** | **String** |  |  [optional] |
|**s3Bucket** | **String** |  |  [optional] |



