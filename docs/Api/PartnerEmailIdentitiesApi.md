# Splashifypro\PartnerEmailIdentitiesApi

All URIs are relative to https://apis.splashifypro.com/api/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**partnerEmailIdentitiesGet()**](PartnerEmailIdentitiesApi.md#partnerEmailIdentitiesGet) | **GET** /partner/email/identities | List sending identities |
| [**partnerEmailIdentitiesPost()**](PartnerEmailIdentitiesApi.md#partnerEmailIdentitiesPost) | **POST** /partner/email/identities | Create sending identity |
| [**partnerEmailIdentitiesTypeValueVerifyPost()**](PartnerEmailIdentitiesApi.md#partnerEmailIdentitiesTypeValueVerifyPost) | **POST** /partner/email/identities/{type}/{value}/verify | Verify identity |


## `partnerEmailIdentitiesGet()`

```php
partnerEmailIdentitiesGet(): array<string,mixed>
```

List sending identities

Returns every verified or pending sending identity (domains + verified email addresses) for the authenticated partner.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: BearerAuth
$config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Splashifypro\Api\PartnerEmailIdentitiesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->partnerEmailIdentitiesGet();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PartnerEmailIdentitiesApi->partnerEmailIdentitiesGet: ', $e->getMessage(), PHP_EOL;
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

## `partnerEmailIdentitiesPost()`

```php
partnerEmailIdentitiesPost($body): array<string,mixed>
```

Create sending identity

Register a new sending identity. For DOMAIN type returns the SPF + DKIM CNAME + DMARC TXT records to publish; for EMAIL_ADDRESS type sends a one-time confirmation token.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: BearerAuth
$config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Splashifypro\Api\PartnerEmailIdentitiesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$body = array('key' => new \stdClass); // object | Create identity payload (identity_type, identity_value)

try {
    $result = $apiInstance->partnerEmailIdentitiesPost($body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PartnerEmailIdentitiesApi->partnerEmailIdentitiesPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **body** | **object**| Create identity payload (identity_type, identity_value) | |

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

## `partnerEmailIdentitiesTypeValueVerifyPost()`

```php
partnerEmailIdentitiesTypeValueVerifyPost($type, $value): array<string,mixed>
```

Verify identity

Re-runs DNS verification (SPF + DKIM + DMARC checks) on a domain identity. Triggered after publishing the DNS records returned from CreateIdentity.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: BearerAuth
$config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Splashifypro\Api\PartnerEmailIdentitiesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$type = 'type_example'; // string | DOMAIN or EMAIL_ADDRESS
$value = 'value_example'; // string | Domain (yourdomain.com) or email address

try {
    $result = $apiInstance->partnerEmailIdentitiesTypeValueVerifyPost($type, $value);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PartnerEmailIdentitiesApi->partnerEmailIdentitiesTypeValueVerifyPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **type** | **string**| DOMAIN or EMAIL_ADDRESS | |
| **value** | **string**| Domain (yourdomain.com) or email address | |

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
