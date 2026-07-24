# Splashifypro\RCSApi

All URIs are relative to https://apis.splashifypro.com/api/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**publicRcsSendPost()**](RCSApi.md#publicRcsSendPost) | **POST** /public/rcs/send | Send an RCS message |
| [**publicRcsSendTemplatePost()**](RCSApi.md#publicRcsSendTemplatePost) | **POST** /public/rcs/send-template | Send an RCS template message |


## `publicRcsSendPost()`

```php
publicRcsSendPost($body): array<string,mixed>
```

Send an RCS message

Send any RCS message type — text, media, card or multiple_cards.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: BearerAuth
$config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Splashifypro\Api\RCSApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$body = array('key' => new \stdClass); // object | RCS message payload (to, type, and the type-specific fields)

try {
    $result = $apiInstance->publicRcsSendPost($body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RCSApi->publicRcsSendPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **body** | **object**| RCS message payload (to, type, and the type-specific fields) | |

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

## `publicRcsSendTemplatePost()`

```php
publicRcsSendTemplatePost($body): array<string,mixed>
```

Send an RCS template message

Send a stored, approved RCS template. Positional {#varN#} placeholders are filled from the variables array, in order.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: BearerAuth
$config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Splashifypro\Api\RCSApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$body = array('key' => new \stdClass); // object | RCS template payload (to, template_id, variables)

try {
    $result = $apiInstance->publicRcsSendTemplatePost($body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RCSApi->publicRcsSendTemplatePost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **body** | **object**| RCS template payload (to, template_id, variables) | |

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
