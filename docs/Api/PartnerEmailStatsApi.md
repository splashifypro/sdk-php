# Splashifypro\PartnerEmailStatsApi

All URIs are relative to https://apis.splashifypro.com/api/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**partnerEmailQuotasGet()**](PartnerEmailStatsApi.md#partnerEmailQuotasGet) | **GET** /partner/email/quotas | Get sending quotas |
| [**partnerEmailStatsGet()**](PartnerEmailStatsApi.md#partnerEmailStatsGet) | **GET** /partner/email/stats | Get sending statistics |


## `partnerEmailQuotasGet()`

```php
partnerEmailQuotasGet(): array<string,mixed>
```

Get sending quotas

Returns the partner's daily send quota, peak send rate, sandbox flag, today's send count, and reputation status. Mirrors AWS SES GetSendQuota.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: BearerAuth
$config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Splashifypro\Api\PartnerEmailStatsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->partnerEmailQuotasGet();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PartnerEmailStatsApi->partnerEmailQuotasGet: ', $e->getMessage(), PHP_EOL;
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

## `partnerEmailStatsGet()`

```php
partnerEmailStatsGet($days, $config_set_id): array<string,mixed>
```

Get sending statistics

Day-by-day counters for sent / delivered / bounced / complained / opened / clicked / rejected over the last N days. Filterable by configuration set.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: BearerAuth
$config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Splashifypro\Api\PartnerEmailStatsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$days = 56; // int | Window size (default 30, max 90)
$config_set_id = 'config_set_id_example'; // string | Filter to one configuration set

try {
    $result = $apiInstance->partnerEmailStatsGet($days, $config_set_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PartnerEmailStatsApi->partnerEmailStatsGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **days** | **int**| Window size (default 30, max 90) | [optional] |
| **config_set_id** | **string**| Filter to one configuration set | [optional] |

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
