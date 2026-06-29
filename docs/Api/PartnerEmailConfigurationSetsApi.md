# Splashifypro\PartnerEmailConfigurationSetsApi

All URIs are relative to https://apis.splashifypro.com/api/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**partnerEmailConfigurationSetsGet()**](PartnerEmailConfigurationSetsApi.md#partnerEmailConfigurationSetsGet) | **GET** /partner/email/configuration-sets | List configuration sets |
| [**partnerEmailConfigurationSetsIdDelete()**](PartnerEmailConfigurationSetsApi.md#partnerEmailConfigurationSetsIdDelete) | **DELETE** /partner/email/configuration-sets/{id} | Delete configuration set |
| [**partnerEmailConfigurationSetsIdGet()**](PartnerEmailConfigurationSetsApi.md#partnerEmailConfigurationSetsIdGet) | **GET** /partner/email/configuration-sets/{id} | Get configuration set |
| [**partnerEmailConfigurationSetsIdPatch()**](PartnerEmailConfigurationSetsApi.md#partnerEmailConfigurationSetsIdPatch) | **PATCH** /partner/email/configuration-sets/{id} | Update configuration set |
| [**partnerEmailConfigurationSetsPost()**](PartnerEmailConfigurationSetsApi.md#partnerEmailConfigurationSetsPost) | **POST** /partner/email/configuration-sets | Create configuration set |


## `partnerEmailConfigurationSetsGet()`

```php
partnerEmailConfigurationSetsGet($customer_id): array<string,mixed>
```

List configuration sets

Returns every configuration set for the authenticated partner. A configuration set is a logical send context — partners typically create one per downstream end-customer or per app surface. Optional customer_id filter scopes the response to one downstream tenant.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: BearerAuth
$config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Splashifypro\Api\PartnerEmailConfigurationSetsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$customer_id = 'customer_id_example'; // string | Filter to one downstream customer

try {
    $result = $apiInstance->partnerEmailConfigurationSetsGet($customer_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PartnerEmailConfigurationSetsApi->partnerEmailConfigurationSetsGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **customer_id** | **string**| Filter to one downstream customer | [optional] |

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

## `partnerEmailConfigurationSetsIdDelete()`

```php
partnerEmailConfigurationSetsIdDelete($id): array<string,mixed>
```

Delete configuration set

Removes a configuration set + its event destinations. Sends already in flight against the deleted set complete normally; future sends referencing the deleted set fall back to \"no config set\" defaults (tracking on, no per-config-set webhooks).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: BearerAuth
$config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Splashifypro\Api\PartnerEmailConfigurationSetsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Config set id

try {
    $result = $apiInstance->partnerEmailConfigurationSetsIdDelete($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PartnerEmailConfigurationSetsApi->partnerEmailConfigurationSetsIdDelete: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Config set id | |

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

## `partnerEmailConfigurationSetsIdGet()`

```php
partnerEmailConfigurationSetsIdGet($id): array<string,mixed>
```

Get configuration set

Returns one configuration set by id, including the current track_opens / track_clicks flags.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: BearerAuth
$config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Splashifypro\Api\PartnerEmailConfigurationSetsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Config set id

try {
    $result = $apiInstance->partnerEmailConfigurationSetsIdGet($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PartnerEmailConfigurationSetsApi->partnerEmailConfigurationSetsIdGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Config set id | |

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

## `partnerEmailConfigurationSetsIdPatch()`

```php
partnerEmailConfigurationSetsIdPatch($id, $body): array<string,mixed>
```

Update configuration set

Patches an existing configuration set. All fields optional — only the keys you supply are updated. Use this to flip track_opens / track_clicks on existing config sets without recreating them.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: BearerAuth
$config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Splashifypro\Api\PartnerEmailConfigurationSetsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Config set id
$body = array('key' => new \stdClass); // object | Any subset of: name, description, suppression_options, reputation_tracking_enabled, sending_enabled, track_opens, track_clicks, custom_redirect_domain, tags.

try {
    $result = $apiInstance->partnerEmailConfigurationSetsIdPatch($id, $body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PartnerEmailConfigurationSetsApi->partnerEmailConfigurationSetsIdPatch: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Config set id | |
| **body** | **object**| Any subset of: name, description, suppression_options, reputation_tracking_enabled, sending_enabled, track_opens, track_clicks, custom_redirect_domain, tags. | |

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

## `partnerEmailConfigurationSetsPost()`

```php
partnerEmailConfigurationSetsPost($body): array<string,mixed>
```

Create configuration set

Creates a new configuration set. New flags track_opens + track_clicks (both default true) control whether Splashify Pro injects the open-tracking pixel + rewrites <a href> URLs through the click-tracking redirect on emails sent through this config set. Set both to false for transactional / privacy-sensitive flows. See partner-docs.splashifypro.com/webhooks/tracking for the full guide.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: BearerAuth
$config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Splashifypro\Api\PartnerEmailConfigurationSetsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$body = array('key' => new \stdClass); // object | Config set fields. Required: name. Optional: description, customer_id, suppression_options (NONE / BOUNCE / COMPLAINT / BOUNCE_AND_COMPLAINT), reputation_tracking_enabled (default true), sending_enabled (default true), track_opens (default true), track_clicks (default true), custom_redirect_domain, tags.

try {
    $result = $apiInstance->partnerEmailConfigurationSetsPost($body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PartnerEmailConfigurationSetsApi->partnerEmailConfigurationSetsPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **body** | **object**| Config set fields. Required: name. Optional: description, customer_id, suppression_options (NONE / BOUNCE / COMPLAINT / BOUNCE_AND_COMPLAINT), reputation_tracking_enabled (default true), sending_enabled (default true), track_opens (default true), track_clicks (default true), custom_redirect_domain, tags. | |

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
