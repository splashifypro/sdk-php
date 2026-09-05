# Splashifypro\ConversationsApi



All URIs are relative to https://apis.splashifypro.com/api/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**appMessagesConversationsConversationIdAssignPost()**](ConversationsApi.md#appMessagesConversationsConversationIdAssignPost) | **POST** /app/messages/conversations/{conversation_id}/assign | Assign or release a conversation |
| [**publicAssignmentPost()**](ConversationsApi.md#publicAssignmentPost) | **POST** /public/assignment | Assign or release a chat |


## `appMessagesConversationsConversationIdAssignPost()`

```php
appMessagesConversationsConversationIdAssignPost($conversation_id, $body): array<string,mixed>
```

Assign or release a conversation

Assigns a conversation to a team member, or releases it when assigned_to is empty — fires team_member_assigned or team_member_unassigned respectively.

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
$conversation_id = 'conversation_id_example'; // string | Conversation ID
$body = array('key' => new \stdClass); // object | { assigned_to: string }, empty string releases

try {
    $result = $apiInstance->appMessagesConversationsConversationIdAssignPost($conversation_id, $body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ConversationsApi->appMessagesConversationsConversationIdAssignPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **conversation_id** | **string**| Conversation ID | |
| **body** | **object**| { assigned_to: string }, empty string releases | |

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

## `publicAssignmentPost()`

```php
publicAssignmentPost($body): array<string,mixed>
```

Assign or release a chat

Routes a conversation to a specific team member by their email address, or releases it when agent_email is empty or omitted. Conversation is identified by the customer's phone number. Both agent and conversation must belong to the authenticated account.

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
$body = array('key' => new \stdClass); // object | Assignment payload: user_phone_number (required), agent_email (empty/omitted releases)

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
| **body** | **object**| Assignment payload: user_phone_number (required), agent_email (empty/omitted releases) | |

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
