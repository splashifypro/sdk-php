# Splashifypro\ConversationsApi



All URIs are relative to https://apis.splashifypro.com/api/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**appMessagesConversationsConversationIdAssignPost()**](ConversationsApi.md#appMessagesConversationsConversationIdAssignPost) | **POST** /app/messages/conversations/{conversation_id}/assign | Assign or release a conversation |
| [**publicAssignmentPost()**](ConversationsApi.md#publicAssignmentPost) | **POST** /public/assignment | Assign or release a chat |
| [**publicTeamsGet()**](ConversationsApi.md#publicTeamsGet) | **GET** /public/teams | List teams |


## `appMessagesConversationsConversationIdAssignPost()`

```php
appMessagesConversationsConversationIdAssignPost($conversation_id, $body): array<string,mixed>
```

Assign or release a conversation

Gives a conversation to a team member, a team or both. Empty assigned_to releases it (back to its team's queue when it has a team). team_id left out keeps the team, \"\" clears it. Fires team_member_assigned, team_member_unassigned or conversation_queued.

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
$body = array('key' => new \stdClass); // object | { assigned_to: string, team_id?: string, note?: string }

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
| **body** | **object**| { assigned_to: string, team_id?: string, note?: string } | |

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

Routes a conversation to a team member by their email address, to a team (team_id or team_name: with no agent_email the chat waits in the team's queue), or both (the person, inside that team). An empty or omitted agent_email with no team releases it. team_id \"\" takes the chat out of its team. The conversation is identified by the customer's phone number. Everything must belong to the authenticated account.

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
$body = array('key' => new \stdClass); // object | user_phone_number (required), agent_email, team_id or team_name (all optional)

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
| **body** | **object**| user_phone_number (required), agent_email, team_id or team_name (all optional) | |

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

## `publicTeamsGet()`

```php
publicTeamsGet(): array<string,mixed>
```

List teams

The account's teams with their people (id, name, team lead or not). Empty when the account has no teams. Use a team_id or team_name with POST /public/assignment.

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

try {
    $result = $apiInstance->publicTeamsGet();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ConversationsApi->publicTeamsGet: ', $e->getMessage(), PHP_EOL;
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
