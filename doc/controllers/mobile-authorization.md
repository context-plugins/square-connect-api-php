# Mobile Authorization

```php
$mobileAuthorizationController = $client->getMobileAuthorizationController();
```

## Class Name

`MobileAuthorizationController`


# Create Mobile Authorization Code

Generates code to authorize a mobile application to connect to a Square card reader

Authorization codes are one-time-use and expire __60 minutes__ after being issued.

__Important:__ The `Authorization` header you provide to this endpoint must have the following format:

```
Authorization: Bearer ACCESS_TOKEN
```

Replace `ACCESS_TOKEN` with a
[valid production authorization credential](https://developer.squareup.com/docs/build-basics/access-tokens).

```php
function createMobileAuthorizationCode(
    CreateMobileAuthorizationCodeRequest $body
): CreateMobileAuthorizationCodeResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`CreateMobileAuthorizationCodeRequest`](../../doc/models/create-mobile-authorization-code-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`PAYMENTS_WRITE_IN_PERSON`

## Response Type

**200**: Success

[`CreateMobileAuthorizationCodeResponse`](../../doc/models/create-mobile-authorization-code-response.md)

## Example Usage

```php
$body = CreateMobileAuthorizationCodeRequestBuilder::init()->build();

$mobileAuthorizationController = $client->getMobileAuthorizationController();

try {
    $result = $mobileAuthorizationController->createMobileAuthorizationCode($body);
    echo 'CreateMobileAuthorizationCodeResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

