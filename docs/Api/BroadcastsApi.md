# Splashifypro\BroadcastsApi



All URIs are relative to https://apis.splashifypro.com/api/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**publicBroadcastsIdAutoRetargetDelete()**](BroadcastsApi.md#publicBroadcastsIdAutoRetargetDelete) | **DELETE** /public/broadcasts/{id}/auto-retarget | Cancel an automatic retarget |
| [**publicBroadcastsIdAutoRetargetGet()**](BroadcastsApi.md#publicBroadcastsIdAutoRetargetGet) | **GET** /public/broadcasts/{id}/auto-retarget | Get a broadcast&#39;s automatic retarget |
| [**publicBroadcastsIdAutoRetargetPost()**](BroadcastsApi.md#publicBroadcastsIdAutoRetargetPost) | **POST** /public/broadcasts/{id}/auto-retarget | Schedule an automatic retarget |


## `publicBroadcastsIdAutoRetargetDelete()`

```php
publicBroadcastsIdAutoRetargetDelete($id): array<string,mixed>
```

Cancel an automatic retarget

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: BearerAuth
$config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Splashifypro\Api\BroadcastsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Broadcast id

try {
    $result = $apiInstance->publicBroadcastsIdAutoRetargetDelete($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling BroadcastsApi->publicBroadcastsIdAutoRetargetDelete: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Broadcast id | |

### Return type

**array<string,mixed>**

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `publicBroadcastsIdAutoRetargetGet()`

```php
publicBroadcastsIdAutoRetargetGet($id): array<string,mixed>
```

Get a broadcast's automatic retarget

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: BearerAuth
$config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Splashifypro\Api\BroadcastsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Broadcast id (GraphQL broadcasts query)

try {
    $result = $apiInstance->publicBroadcastsIdAutoRetargetGet($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling BroadcastsApi->publicBroadcastsIdAutoRetargetGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Broadcast id (GraphQL broadcasts query) | |

### Return type

**array<string,mixed>**

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `publicBroadcastsIdAutoRetargetPost()`

```php
publicBroadcastsIdAutoRetargetPost($id, $body): array<string,mixed>
```

Schedule an automatic retarget

After delay_hours (1 to 72), sends a follow-up to the people who got the broadcast but did not read it. Same template unless template_id is given (WhatsApp only), with template_params as a JSON string of its components. Charged like any broadcast when it sends.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: BearerAuth
$config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Splashifypro\Api\BroadcastsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Broadcast id
$body = array('key' => new \stdClass); // object | { delay_hours, consent_attested: true, template_id?, template_params? }

try {
    $result = $apiInstance->publicBroadcastsIdAutoRetargetPost($id, $body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling BroadcastsApi->publicBroadcastsIdAutoRetargetPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Broadcast id | |
| **body** | **object**| { delay_hours, consent_attested: true, template_id?, template_params? } | |

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
