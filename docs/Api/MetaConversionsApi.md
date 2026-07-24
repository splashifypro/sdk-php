# Splashifypro\MetaConversionsApi

All URIs are relative to https://apis.splashifypro.com/api/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**publicCapiSendEventPost()**](MetaConversionsApi.md#publicCapiSendEventPost) | **POST** /public/capi/send-event | Send a Meta Conversion API event |


## `publicCapiSendEventPost()`

```php
publicCapiSendEventPost($body): array<string,mixed>
```

Send a Meta Conversion API event

Fire a server-side Meta Pixel / Conversions API event for a contact identified by phone number. Useful for ROI attribution on Click-to-WhatsApp ads. Event names: Lead, Purchase, AddToCart, etc. Requires Meta Ads OAuth completed in the dashboard.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: BearerAuth
$config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Splashifypro\Api\MetaConversionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$body = array('key' => new \stdClass); // object | CAPI payload (event_name, phone_number, value, currency)

try {
    $result = $apiInstance->publicCapiSendEventPost($body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MetaConversionsApi->publicCapiSendEventPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **body** | **object**| CAPI payload (event_name, phone_number, value, currency) | |

### Return type

**array<string,mixed>**

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
