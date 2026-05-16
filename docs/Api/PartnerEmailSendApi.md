# Splashifypro\PartnerEmailSendApi

All URIs are relative to https://apis.splashifypro.com/api/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**partnerEmailEmailsMessageIdGet()**](PartnerEmailSendApi.md#partnerEmailEmailsMessageIdGet) | **GET** /partner/email/emails/{message_id} | Get email status |
| [**partnerEmailSendBulkPost()**](PartnerEmailSendApi.md#partnerEmailSendBulkPost) | **POST** /partner/email/send-bulk | Send bulk templated email |
| [**partnerEmailSendPost()**](PartnerEmailSendApi.md#partnerEmailSendPost) | **POST** /partner/email/send | Send email |
| [**partnerEmailSendRawPost()**](PartnerEmailSendApi.md#partnerEmailSendRawPost) | **POST** /partner/email/send-raw | Send raw MIME email |
| [**partnerEmailSendTemplatePost()**](PartnerEmailSendApi.md#partnerEmailSendTemplatePost) | **POST** /partner/email/send-template | Send templated email |


## `partnerEmailEmailsMessageIdGet()`

```php
partnerEmailEmailsMessageIdGet($message_id): array<string,mixed>
```

Get email status

Look up the current status and event timeline for an email by message_id. Returns sent / delivered / bounced / complained state plus open + click counters.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: BearerAuth
$config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Splashifypro\Api\PartnerEmailSendApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$message_id = 'message_id_example'; // string | Message ID returned from /send

try {
    $result = $apiInstance->partnerEmailEmailsMessageIdGet($message_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PartnerEmailSendApi->partnerEmailEmailsMessageIdGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **message_id** | **string**| Message ID returned from /send | |

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

## `partnerEmailSendBulkPost()`

```php
partnerEmailSendBulkPost($body): array<string,mixed>
```

Send bulk templated email

One template + one verified From + N destinations, each with its own ReplacementData map. Equivalent to AWS SES SendBulkTemplatedEmail. Caps: 50 destinations × 50 recipients = 500 total per request.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: BearerAuth
$config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Splashifypro\Api\PartnerEmailSendApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$body = array('key' => new \stdClass); // object | Send bulk payload (template_name, from, default_template_data, destinations[])

try {
    $result = $apiInstance->partnerEmailSendBulkPost($body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PartnerEmailSendApi->partnerEmailSendBulkPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **body** | **object**| Send bulk payload (template_name, from, default_template_data, destinations[]) | |

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

## `partnerEmailSendPost()`

```php
partnerEmailSendPost($body): array<string,mixed>
```

Send email

Send a transactional or marketing email to up to 50 recipients (combined to + cc + bcc). Equivalent to AWS SES SendEmail.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: BearerAuth
$config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Splashifypro\Api\PartnerEmailSendApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$body = array('key' => new \stdClass); // object | Send email payload (from, to, subject, html_body, text_body, configuration_set_name?)

try {
    $result = $apiInstance->partnerEmailSendPost($body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PartnerEmailSendApi->partnerEmailSendPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **body** | **object**| Send email payload (from, to, subject, html_body, text_body, configuration_set_name?) | |

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

## `partnerEmailSendRawPost()`

```php
partnerEmailSendRawPost($body): array<string,mixed>
```

Send raw MIME email

Submit a pre-built RFC 5322 MIME message — useful when you've already constructed the email body yourself (DKIM-ready, multipart, calendar invites, etc). Equivalent to AWS SES SendRawEmail. Max 10 MiB raw body.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: BearerAuth
$config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Splashifypro\Api\PartnerEmailSendApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$body = array('key' => new \stdClass); // object | Send raw payload (raw_message_base64, destinations[], from, configuration_set_name?)

try {
    $result = $apiInstance->partnerEmailSendRawPost($body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PartnerEmailSendApi->partnerEmailSendRawPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **body** | **object**| Send raw payload (raw_message_base64, destinations[], from, configuration_set_name?) | |

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

## `partnerEmailSendTemplatePost()`

```php
partnerEmailSendTemplatePost($body): array<string,mixed>
```

Send templated email

Render a saved template with per-recipient variables and send it. Equivalent to AWS SES SendTemplatedEmail. Templates are pre-rendered at save time so per-send substitution is cheap.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: BearerAuth
$config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Splashifypro\Api\PartnerEmailSendApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$body = array('key' => new \stdClass); // object | Send template payload (template_name OR template_id, from, to[], variables{})

try {
    $result = $apiInstance->partnerEmailSendTemplatePost($body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PartnerEmailSendApi->partnerEmailSendTemplatePost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **body** | **object**| Send template payload (template_name OR template_id, from, to[], variables{}) | |

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
