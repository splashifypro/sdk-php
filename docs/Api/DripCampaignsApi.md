# Splashifypro\DripCampaignsApi



All URIs are relative to https://apis.splashifypro.com/api/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**publicDripCampaignsGet()**](DripCampaignsApi.md#publicDripCampaignsGet) | **GET** /public/drip/campaigns | List drip campaigns |
| [**publicDripStartPost()**](DripCampaignsApi.md#publicDripStartPost) | **POST** /public/drip/start | Start a drip campaign for a contact |


## `publicDripCampaignsGet()`

```php
publicDripCampaignsGet(): array<string,mixed>
```

List drip campaigns

Returns this account's drip campaigns with their id, name and status. Use the campaign_id with the start endpoint.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Splashifypro\Api\DripCampaignsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);

try {
    $result = $apiInstance->publicDripCampaignsGet();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DripCampaignsApi->publicDripCampaignsGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

**array<string,mixed>**

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `publicDripStartPost()`

```php
publicDripStartPost($request): array<string,mixed>
```

Start a drip campaign for a contact

Enrols one contact into a drip campaign. The first message goes out after that step's configured wait, and the rest follow on their own schedule. The campaign must be running. Safe to call twice — a contact already in the campaign is reported, not enrolled again.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new Splashifypro\Api\DripCampaignsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$request = array('key' => new \stdClass); // object | campaign_id and phone_number

try {
    $result = $apiInstance->publicDripStartPost($request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DripCampaignsApi->publicDripStartPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **request** | **object**| campaign_id and phone_number | |

### Return type

**array<string,mixed>**

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
