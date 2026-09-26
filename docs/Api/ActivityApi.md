# Splashifypro\ActivityApi



All URIs are relative to https://apis.splashifypro.com/api/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**appActivityLogsGet()**](ActivityApi.md#appActivityLogsGet) | **GET** /app/activity-logs | List activity logs |


## `appActivityLogsGet()`

```php
appActivityLogsGet($action, $entity_type, $entity_id, $actor_id, $limit, $cursor): array<string,mixed>
```

List activity logs

Paginated audit trail of account activity. total is a real row count; page with cursor/next_cursor, not offset.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: BearerAuth
$config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Splashifypro\Api\ActivityApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$action = 'action_example'; // string | Filter by action
$entity_type = 'entity_type_example'; // string | Filter by entity type
$entity_id = 'entity_id_example'; // string | Filter by entity id
$actor_id = 'actor_id_example'; // string | Filter by actor id
$limit = 56; // int | Page size, default 50, max 200
$cursor = 'cursor_example'; // string | Opaque cursor from a previous response's next_cursor

try {
    $result = $apiInstance->appActivityLogsGet($action, $entity_type, $entity_id, $actor_id, $limit, $cursor);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ActivityApi->appActivityLogsGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **action** | **string**| Filter by action | [optional] |
| **entity_type** | **string**| Filter by entity type | [optional] |
| **entity_id** | **string**| Filter by entity id | [optional] |
| **actor_id** | **string**| Filter by actor id | [optional] |
| **limit** | **int**| Page size, default 50, max 200 | [optional] |
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
