# Splashify Pro — PHP SDK

[![Packagist](https://img.shields.io/badge/packagist-splashifypro%2Fsdk-f28d1a?logo=packagist&logoColor=white)](https://packagist.org/packages/splashifypro/sdk)
[![PHP](https://img.shields.io/badge/php-8.1%2B-777bb4?logo=php&logoColor=white)](https://packagist.org/packages/splashifypro/sdk)
[![docs](https://img.shields.io/badge/docs-splashifypro.com-1B70FF)](https://docs.splashifypro.com/public-api)
[![license](https://img.shields.io/badge/license-MIT-22c55e)](./LICENSE)

Official PHP SDK for the [Splashify Pro](https://splashifypro.com) API —
send WhatsApp messages, transactional emails, manage contacts and
conversations, and fire Meta Conversions events from your PHP application
(Laravel, Symfony, WordPress, plain PHP — all supported).

## Install

```bash
composer require splashifypro/sdk
```

Requires PHP 8.1+.

## Get your API key

1. **Sign in** to your Splashify Pro account at
   [app.splashifypro.com](https://app.splashifypro.com).
   No account yet? [Sign up free](https://app.splashifypro.com/auth/signup).

2. Open the **Settings** dialog (gear icon, top right) → click the
   **Developer** tile.
   *Direct link:* [app.splashifypro.com/settings/developer](https://app.splashifypro.com/settings/developer)

3. Under **API Keys**, click **Generate Secret Key**.

4. Copy the key shown (starts with `sk_live_…`) and store it somewhere
   secure — it's shown **only once**. If you lose it, generate a new one
   and the old one stops working.

5. Use it as the `SPLASHIFY_API_KEY` environment variable in your app.
   **Never commit it to git or paste it into client-side code** — the
   key carries full account access.

> **Tip:** Set up a [webhook URL](https://app.splashifypro.com/settings/developer)
> on the same page to receive delivery / read receipts and inbound message
> events.

## Authentication

The SDK uses HTTP Basic with the API key as the username:

```php
<?php
require 'vendor/autoload.php';

use Splashifypro\Configuration;
use Splashifypro\Api\MessagesApi;
use GuzzleHttp\Client;

$config = Configuration::getDefaultConfiguration()
    ->setUsername(getenv('SPLASHIFY_API_KEY'));

$messages = new MessagesApi(new Client(), $config);
```

## Quickstart — send a WhatsApp text

```php
$result = $messages->publicMessagePost([
    'type' => 'Text',
    'countryCode' => '+91',
    'phoneNumber' => '9999999999',
    'data' => ['message' => 'Hi! Thanks for reaching out 👋'],
]);

echo $result['id']; // message_id — use to poll status / correlate webhooks
```

## Send a WhatsApp template

```php
$messages->publicMessagePost([
    'type' => 'Template',
    'countryCode' => '+91',
    'phoneNumber' => '9999999999',
    'template' => [
        'name' => 'order_confirmation',
        'languageCode' => 'en',
        'bodyValues' => ['Sayan', 'ORD-1042', '₹1,499'],
        'buttonValues' => ['0' => ['https://shop.example.com/orders/1042']],
    ],
]);
```

## Send a transactional email

> Requires a verified sender domain. Set up at
> **https://app.splashifypro.com/settings/email-domain**.

```php
use Splashifypro\Api\EmailApi;

$email = new EmailApi(new Client(), $config);

$email->publicEmailSendPost([
    'to' => 'customer@example.com',
    'subject' => 'Your receipt for Order #1042',
    'html' => '<h1>Thanks!</h1><p>Order #1042 confirmed.</p>',
    'text' => 'Thanks! Order #1042 confirmed.',
    'from_email' => 'billing@yourdomain.com',
    'from_name' => 'Acme Inc.',
]);
```

## Available APIs

| Class                | What it does                                                |
| -------------------- | ----------------------------------------------------------- |
| `MessagesApi`        | Send WhatsApp messages (text, template, media, interactive) |
| `EmailApi`           | Send transactional + templated emails                       |
| `ContactsApi`        | List + filter contacts                                      |
| `ConversationsApi`   | Assign chats to team members                                |
| `MetaConversionsApi` | Fire Meta Pixel / Conversions API events                    |

Full reference, request/response shapes, and per-endpoint examples:
**https://docs.splashifypro.com/public-api**

## Laravel example

```php
// In a service or controller
use Splashifypro\Configuration;
use Splashifypro\Api\MessagesApi;
use GuzzleHttp\Client;

class WhatsAppService
{
    private MessagesApi $messages;

    public function __construct()
    {
        $config = Configuration::getDefaultConfiguration()
            ->setUsername(config('services.splashifypro.key'));
        $this->messages = new MessagesApi(new Client(), $config);
    }

    public function sendOtp(string $phone, string $code): void
    {
        $this->messages->publicMessagePost([
            'type' => 'Template',
            'phoneNumber' => $phone,
            'template' => [
                'name' => 'verification_code',
                'languageCode' => 'en',
                'bodyValues' => [$code],
            ],
        ]);
    }
}
```

Add to `config/services.php`:

```php
'splashifypro' => [
    'key' => env('SPLASHIFY_API_KEY'),
],
```

## Error handling

```php
use Splashifypro\ApiException;

try {
    $result = $messages->publicMessagePost([...]);
} catch (ApiException $e) {
    error_log("HTTP " . $e->getCode() . ": " . $e->getResponseBody());
}
```

## Rate limits

Per-key limits depend on your plan tier. Hitting the limit returns HTTP 429 —
the response body includes `Retry-After`. Tier and current consumption are
visible at https://app.splashifypro.com/settings/developer.

## Support

- **Issues / bug reports:** [github.com/splashifypro/sdk-php/issues](https://github.com/splashifypro/sdk-php/issues)
- **Documentation:** [docs.splashifypro.com/public-api](https://docs.splashifypro.com/public-api)
- **Email support:** support@splashifypro.in

## License

[MIT](./LICENSE)

---

This SDK is auto-generated from the official OpenAPI specification. Pull
requests for SDK-side improvements (typing, ergonomic wrappers, framework
adapters, etc.) are welcome; underlying API changes should be filed against
the documentation site.
