# Splashifypro\ExpensesApi



All URIs are relative to https://apis.splashifypro.com/api/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**appExpensesBillingLogsGet()**](ExpensesApi.md#appExpensesBillingLogsGet) | **GET** /app/expenses/billing-logs | Billing log entries |
| [**appExpensesSummaryGet()**](ExpensesApi.md#appExpensesSummaryGet) | **GET** /app/expenses/summary | Expense summary |


## `appExpensesBillingLogsGet()`

```php
appExpensesBillingLogsGet($period, $limit, $cursor): array<string,mixed>
```

Billing log entries

Paginated per-message deduction log. total is a real count of billable rows for the period, not the size of one page; page with cursor/next_cursor.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: BearerAuth
$config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Splashifypro\Api\ExpensesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$period = 'period_example'; // string | 7d, 30d, 3m, 6m, or all — default 30d
$limit = 56; // int | Page size, default 100, max 500
$cursor = 'cursor_example'; // string | Opaque cursor from a previous response's next_cursor

try {
    $result = $apiInstance->appExpensesBillingLogsGet($period, $limit, $cursor);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ExpensesApi->appExpensesBillingLogsGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **period** | **string**| 7d, 30d, 3m, 6m, or all — default 30d | [optional] |
| **limit** | **int**| Page size, default 100, max 500 | [optional] |
| **cursor** | **string**| Opaque cursor from a previous response&#39;s next_cursor | [optional] |

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

## `appExpensesSummaryGet()`

```php
appExpensesSummaryGet($period): array<string,mixed>
```

Expense summary

Message deduction stats: total spent, breakdown by category, total messages, and real sent/delivered counts from WhatsApp status (not the account's billing-timing preference). period in the response is the resolved value, not the raw query param — an unrecognised value silently falls back to 30d.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: BearerAuth
$config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Splashifypro\Api\ExpensesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$period = 'period_example'; // string | 7d, 30d, 3m, 6m, or all — default 30d

try {
    $result = $apiInstance->appExpensesSummaryGet($period);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ExpensesApi->appExpensesSummaryGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **period** | **string**| 7d, 30d, 3m, 6m, or all — default 30d | [optional] |

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
