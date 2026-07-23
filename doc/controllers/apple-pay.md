# Apple Pay

```php
$applePayController = $client->getApplePayController();
```

## Class Name

`ApplePayController`


# Register Domain

Activates a domain for use with Apple Pay on the Web and Square. A validation
is performed on this domain by Apple to ensure that it is properly set up as
an Apple Pay enabled domain.

This endpoint provides an easy way for platform developers to bulk activate
Apple Pay on the Web with Square for merchants using their platform.

To learn more about Web Apple Pay, see
[Add the Apple Pay on the Web Button](https://developer.squareup.com/docs/payment-form/add-digital-wallets/apple-pay).

```php
function registerDomain(RegisterDomainRequest $body): RegisterDomainResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`RegisterDomainRequest`](../../doc/models/register-domain-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Response Type

**200**: Success

[`RegisterDomainResponse`](../../doc/models/register-domain-response.md)

## Example Usage

```php
$body = RegisterDomainRequestBuilder::init(
    'domain_name0'
)->build();

$applePayController = $client->getApplePayController();

try {
    $result = $applePayController->registerDomain($body);
    echo 'RegisterDomainResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

