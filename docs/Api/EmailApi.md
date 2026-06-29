# Splashifypro\EmailApi

All URIs are relative to https://apis.splashifypro.com/api/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**publicEmailSendPost()**](EmailApi.md#publicEmailSendPost) | **POST** /public/email/send | Send a transactional email |
| [**publicEmailSendTemplatePost()**](EmailApi.md#publicEmailSendTemplatePost) | **POST** /public/email/send-template | Send a templated email |
| [**publicEmailStatusMessageIdGet()**](EmailApi.md#publicEmailStatusMessageIdGet) | **GET** /public/email/status/{message_id} | Get email delivery status |


## `publicEmailSendPost()`

```php
publicEmailSendPost($body): array<string,mixed>
```

Send a transactional email

Send a fully-formed HTML email to one or more recipients. Caller supplies subject + html + text + from_email + recipient. Optional attachments[] (PDFs, images, docs) ride inline as base64 — backend builds multipart/mixed and DKIM-signs. Caps: 20 files / 10 MiB total / executable extensions blocked. Delivered via the platform's self-hosted email pipeline with category=email_transactional. From-email must be on a verified sender domain.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: BearerAuth
$config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Splashifypro\Api\EmailApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$body = array('key' => new \stdClass); // object | Send email payload (to, subject, html, text, from_email, reply_to, attachments)

try {
    $result = $apiInstance->publicEmailSendPost($body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling EmailApi->publicEmailSendPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **body** | **object**| Send email payload (to, subject, html, text, from_email, reply_to, attachments) | |

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

## `publicEmailSendTemplatePost()`

```php
publicEmailSendTemplatePost($body): array<string,mixed>
```

Send a templated email

Send an email using a saved template (created via the in-app template editor at /email/templates). Caller supplies template_id + recipient + variables map. Backend pulls the template's pre-rendered HTML and substitutes {{vars}}. Optional attachments[] ride inline as base64 — same shape + caps as /send (20 files / 10 MiB / blocked extensions).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: BearerAuth
$config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Splashifypro\Api\EmailApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$body = array('key' => new \stdClass); // object | Template send payload (to, template_id, variables, from_email, subject, attachments)

try {
    $result = $apiInstance->publicEmailSendTemplatePost($body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling EmailApi->publicEmailSendTemplatePost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **body** | **object**| Template send payload (to, template_id, variables, from_email, subject, attachments) | |

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

## `publicEmailStatusMessageIdGet()`

```php
publicEmailStatusMessageIdGet($message_id): array<string,mixed>
```

Get email delivery status

Look up the current status of an email message by its message_id (returned from /public/email/send or /send-template). Status values: queued, sending, delivered, bounced, failed.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: BearerAuth
$config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Splashifypro\Api\EmailApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$message_id = 'message_id_example'; // string | Message ID returned by send

try {
    $result = $apiInstance->publicEmailStatusMessageIdGet($message_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling EmailApi->publicEmailStatusMessageIdGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **message_id** | **string**| Message ID returned by send | |

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
