# Splashifypro\ConversationsApi

All URIs are relative to https://apis.splashifypro.com/api/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**publicAssignmentPost()**](ConversationsApi.md#publicAssignmentPost) | **POST** /public/assignment | Assign a chat to a team member |


## `publicAssignmentPost()`

```php
publicAssignmentPost($body): array<string,mixed>
```

Assign a chat to a team member

Routes a conversation to a specific team member by their email address. Conversation is identified by the customer's phone number. Both must belong to the authenticated account.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: BearerAuth
$config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Splashifypro\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Splashifypro\Api\ConversationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$body = array('key' => new \stdClass); // object | Assignment payload (user_phone_number, agent_email)

try {
    $result = $apiInstance->publicAssignmentPost($body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ConversationsApi->publicAssignmentPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **body** | **object**| Assignment payload (user_phone_number, agent_email) | |

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
