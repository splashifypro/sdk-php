# Splashifypro\MessagesApi



All URIs are relative to https://apis.splashifypro.com/api/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**appMessagesSendMediaPost()**](MessagesApi.md#appMessagesSendMediaPost) | **POST** /app/messages/send-media | Send a media message |
| [**appMessagesTypingIndicatorPost()**](MessagesApi.md#appMessagesTypingIndicatorPost) | **POST** /app/messages/typing-indicator | Send a typing indicator |
| [**publicMessagePost()**](MessagesApi.md#publicMessagePost) | **POST** /public/message | Send a WhatsApp message |


## `appMessagesSendMediaPost()`

```php
appMessagesSendMediaPost($body): array<string,mixed>
```

Send a media message

Sends an image, video, audio, or document message. Pass either media_url (any public URL) or media_id (a file previously uploaded via POST /app/media) — not both required.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: BearerAuth
$config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Splashifypro\Api\MessagesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$body = array('key' => new \stdClass); // object | { to, media_type, media_url|media_id, caption?, filename?, voice? }

try {
    $result = $apiInstance->appMessagesSendMediaPost($body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MessagesApi->appMessagesSendMediaPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **body** | **object**| { to, media_type, media_url|media_id, caption?, filename?, voice? } | |

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

## `appMessagesTypingIndicatorPost()`

```php
appMessagesTypingIndicatorPost($body): array<string,mixed>
```

Send a typing indicator

Shows the typing indicator on the given inbound message's conversation. WhatsApp dismisses it after ~25s or on the next message from this business, whichever comes first.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: BearerAuth
$config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Splashifypro\Api\MessagesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$body = array('key' => new \stdClass); // object | { message_id: string }

try {
    $result = $apiInstance->appMessagesTypingIndicatorPost($body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MessagesApi->appMessagesTypingIndicatorPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **body** | **object**| { message_id: string } | |

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

## `publicMessagePost()`

```php
publicMessagePost($body): array<string,mixed>
```

Send a WhatsApp message

Send any supported WhatsApp message type to a contact. See type-specific request examples in the per-message docs.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: BearerAuth
$config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Splashifypro\Api\MessagesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$body = array('key' => new \stdClass); // object | Send message payload (type, phoneNumber, data)

try {
    $result = $apiInstance->publicMessagePost($body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MessagesApi->publicMessagePost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **body** | **object**| Send message payload (type, phoneNumber, data) | |

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
