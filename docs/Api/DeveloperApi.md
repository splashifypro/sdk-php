# Splashifypro\DeveloperApi



All URIs are relative to https://apis.splashifypro.com/api/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**appDeveloperOptOutErrorPut()**](DeveloperApi.md#appDeveloperOptOutErrorPut) | **PUT** /app/developer/opt-out-error | Toggle opt-out send errors |
| [**appDeveloperSecretKeyGeneratePost()**](DeveloperApi.md#appDeveloperSecretKeyGeneratePost) | **POST** /app/developer/secret-key/generate | Generate (or regenerate) the API secret key |
| [**appDeveloperSettingsGet()**](DeveloperApi.md#appDeveloperSettingsGet) | **GET** /app/developer/settings | Get developer settings |
| [**appDeveloperWebhookPut()**](DeveloperApi.md#appDeveloperWebhookPut) | **PUT** /app/developer/webhook | Configure the console webhook |


## `appDeveloperOptOutErrorPut()`

```php
appDeveloperOptOutErrorPut($body): array<string,mixed>
```

Toggle opt-out send errors

When enabled, the Message Send API returns an error instead of silently no-op'ing when called for a contact who has opted out.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: BearerAuth
$config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Splashifypro\Api\DeveloperApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$body = new \Splashifypro\Model\HandlersUpdateOptOutErrorRequest(); // \Splashifypro\Model\HandlersUpdateOptOutErrorRequest | { enabled: boolean }

try {
    $result = $apiInstance->appDeveloperOptOutErrorPut($body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DeveloperApi->appDeveloperOptOutErrorPut: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **body** | [**\Splashifypro\Model\HandlersUpdateOptOutErrorRequest**](../Model/HandlersUpdateOptOutErrorRequest.md)| { enabled: boolean } | |

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

## `appDeveloperSecretKeyGeneratePost()`

```php
appDeveloperSecretKeyGeneratePost(): array<string,mixed>
```

Generate (or regenerate) the API secret key

Invalidates any existing sk_live_ key immediately. This is the Authorization key for /api/v1/public/_* requests — a different secret from any webhook's signing secret.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: BearerAuth
$config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Splashifypro\Api\DeveloperApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->appDeveloperSecretKeyGeneratePost();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DeveloperApi->appDeveloperSecretKeyGeneratePost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

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

## `appDeveloperSettingsGet()`

```php
appDeveloperSettingsGet(): array<string,mixed>
```

Get developer settings

webhook_id/webhook_secret/webhook_active describe the real app_webhooks row backing this page's Configure Webhook editor — the same object GET /app/webhooks lists and POST /app/webhooks/{id}/rotate-secret operates on. Deliveries to webhook_url are signed with webhook_secret exactly like any webhook created through that API.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: BearerAuth
$config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Splashifypro\Api\DeveloperApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->appDeveloperSettingsGet();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DeveloperApi->appDeveloperSettingsGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

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

## `appDeveloperWebhookPut()`

```php
appDeveloperWebhookPut($body): array<string,mixed>
```

Configure the console webhook

Creates or updates the single app_webhooks row backing this page — its id and signing secret stay stable across edits, so changing the URL never invalidates signature verification. Deliveries are signed exactly like a webhook created via POST /app/webhooks (same headers, same HMAC scheme) — see Verifying signatures in the webhooks guide. An empty webhook_url deactivates it without deleting it; reconfiguring later reuses the same id and secret. Manage it like any other webhook via GET/PATCH/DELETE /app/webhooks/{id} and /rotate-secret using the webhook_id returned by GET /app/developer/settings.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: BearerAuth
$config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Splashifypro\Api\DeveloperApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$body = new \Splashifypro\Model\HandlersUpdateWebhookRequest(); // \Splashifypro\Model\HandlersUpdateWebhookRequest | { webhook_url: string, webhook_events: string[] }

try {
    $result = $apiInstance->appDeveloperWebhookPut($body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DeveloperApi->appDeveloperWebhookPut: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **body** | [**\Splashifypro\Model\HandlersUpdateWebhookRequest**](../Model/HandlersUpdateWebhookRequest.md)| { webhook_url: string, webhook_events: string[] } | |

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
