# Splashifypro\SMSApi



All URIs are relative to https://apis.splashifypro.com/api/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**publicSmsBulkBulkIdGet()**](SMSApi.md#publicSmsBulkBulkIdGet) | **GET** /public/sms/bulk/{bulk_id} | Bulk send progress |
| [**publicSmsMessagesMessageIdGet()**](SMSApi.md#publicSmsMessagesMessageIdGet) | **GET** /public/sms/messages/{message_id} | One SMS status |
| [**publicSmsSendBulkPost()**](SMSApi.md#publicSmsSendBulkPost) | **POST** /public/sms/send-bulk | Send one template to many numbers |
| [**publicSmsSendPost()**](SMSApi.md#publicSmsSendPost) | **POST** /public/sms/send | Send one SMS |
| [**publicSmsSendersGet()**](SMSApi.md#publicSmsSendersGet) | **GET** /public/sms/senders | SMS sender IDs |
| [**publicSmsTemplatesGet()**](SMSApi.md#publicSmsTemplatesGet) | **GET** /public/sms/templates | Approved SMS templates |


## `publicSmsBulkBulkIdGet()`

```php
publicSmsBulkBulkIdGet($bulk_id): array<string,mixed>
```

Bulk send progress

Progress of a bulk send by the bulk_id /public/sms/send-bulk returned. status is queued, running, completed, stopped or cancelled. failed counts numbers the network refused plus delivery failures reported so far.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: BearerAuth
$config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Splashifypro\Api\SMSApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$bulk_id = 'bulk_id_example'; // string | bulk_id from /public/sms/send-bulk

try {
    $result = $apiInstance->publicSmsBulkBulkIdGet($bulk_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SMSApi->publicSmsBulkBulkIdGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **bulk_id** | **string**| bulk_id from /public/sms/send-bulk | |

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

## `publicSmsMessagesMessageIdGet()`

```php
publicSmsMessagesMessageIdGet($message_id): array<string,mixed>
```

One SMS status

Status of one message by the message_id /public/sms/send returned. status is queued, sent, delivered, failed or rejected. error says why when it did not arrive.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: BearerAuth
$config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Splashifypro\Api\SMSApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$message_id = 'message_id_example'; // string | message_id from /public/sms/send

try {
    $result = $apiInstance->publicSmsMessagesMessageIdGet($message_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SMSApi->publicSmsMessagesMessageIdGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **message_id** | **string**| message_id from /public/sms/send | |

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

## `publicSmsSendBulkPost()`

```php
publicSmsSendBulkPost($body, $idempotency_key): array<string,mixed>
```

Send one template to many numbers

Queues 1 to 1,000 messages on one approved template of any DLT type. Every row is checked first. A wrong variable count is a 400 naming the row. Invalid numbers, repeats and opted-out contacts are skipped and counted. Refused with 402 and nothing queued when the wallet cannot cover the estimate.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: BearerAuth
$config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Splashifypro\Api\SMSApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$body = array('key' => new \stdClass); // object | { dlt_template_id, name?, messages: [{ to, variables[] }] }
$idempotency_key = 'idempotency_key_example'; // string | Makes a retry safe: a repeat within 24 hours gets the same bulk_id back with its current status and replayed true, and nothing is queued again

try {
    $result = $apiInstance->publicSmsSendBulkPost($body, $idempotency_key);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SMSApi->publicSmsSendBulkPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **body** | **object**| { dlt_template_id, name?, messages: [{ to, variables[] }] } | |
| **idempotency_key** | **string**| Makes a retry safe: a repeat within 24 hours gets the same bulk_id back with its current status and replayed true, and nothing is queued again | [optional] |

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

## `publicSmsSendPost()`

```php
publicSmsSendPost($body, $idempotency_key): array<string,mixed>
```

Send one SMS

Sends one DLT SMS from an approved template to an Indian mobile number. The template decides the DLT type, the sender ID and the price. variables fill the template's {#var#} slots in order, 30 characters at most each. A message the network refuses is a 200 with accepted false.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: BearerAuth
$config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Splashifypro\Api\SMSApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$body = array('key' => new \stdClass); // object | { to, dlt_template_id, variables[] }
$idempotency_key = 'idempotency_key_example'; // string | Makes a retry safe: a repeat within 24 hours gets the first answer back with replayed true, and nothing is sent again

try {
    $result = $apiInstance->publicSmsSendPost($body, $idempotency_key);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SMSApi->publicSmsSendPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **body** | **object**| { to, dlt_template_id, variables[] } | |
| **idempotency_key** | **string**| Makes a retry safe: a repeat within 24 hours gets the first answer back with replayed true, and nothing is sent again | [optional] |

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

## `publicSmsSendersGet()`

```php
publicSmsSendersGet(): array<string,mixed>
```

SMS sender IDs

The sender IDs on the account. status is approved, pending or rejected; type is the DLT type the sender ID was registered for.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: BearerAuth
$config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Splashifypro\Api\SMSApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->publicSmsSendersGet();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SMSApi->publicSmsSendersGet: ', $e->getMessage(), PHP_EOL;
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

## `publicSmsTemplatesGet()`

```php
publicSmsTemplatesGet(): array<string,mixed>
```

Approved SMS templates

The approved DLT templates on the account. type is promotional, transactional, service_implicit or service_explicit; variables is how many {#var#} slots the body has.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: BearerAuth
$config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Splashifypro\Api\SMSApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->publicSmsTemplatesGet();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SMSApi->publicSmsTemplatesGet: ', $e->getMessage(), PHP_EOL;
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
