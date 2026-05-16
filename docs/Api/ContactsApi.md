# Splashifypro\ContactsApi

All URIs are relative to https://apis.splashifypro.com/api/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**publicApisUsersPost()**](ContactsApi.md#publicApisUsersPost) | **POST** /public/apis/users | List contacts (paginated, filterable) |


## `publicApisUsersPost()`

```php
publicApisUsersPost($offset, $limit, $body): array<string,mixed>
```

List contacts (paginated, filterable)

Returns a paginated list of contacts (customers) for the authenticated account. Filters are applied in-memory and support traits: created_at_utc, modified_at_utc, phone_number, name, email, whatsapp_opted_in, plus any custom column from the contact's column_data.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: BearerAuth
$config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Splashifypro\Api\ContactsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$offset = 56; // int | Pagination offset (default 0)
$limit = 56; // int | Page size (default 100, max 500)
$body = array('key' => new \stdClass); // object | Optional filter object: {filters:[{trait,op,val}]}

try {
    $result = $apiInstance->publicApisUsersPost($offset, $limit, $body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ContactsApi->publicApisUsersPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **offset** | **int**| Pagination offset (default 0) | [optional] |
| **limit** | **int**| Page size (default 100, max 500) | [optional] |
| **body** | **object**| Optional filter object: {filters:[{trait,op,val}]} | [optional] |

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
