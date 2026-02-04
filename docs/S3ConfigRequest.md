

# S3ConfigRequest

Request model for S3 configuration

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**endpointUrl** | **String** | S3-compatible endpoint URL. Must start with https:// |  |
|**accessKeyId** | **String** | Access key ID for S3 authentication |  |
|**secretAccessKey** | **String** |  |  [optional] |
|**bucketName** | **String** | S3 bucket name. Must follow S3 naming conventions (lowercase, no underscores) |  |
|**defaultPrefix** | **String** | Default path prefix for uploaded files. Can include slashes for folder structure |  [optional] |



