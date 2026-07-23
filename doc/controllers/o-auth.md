# O Auth

```php
$oAuthController = $client->getOAuthController();
```

## Class Name

`OAuthController`

## Methods

* [Renew Token](../../doc/controllers/o-auth.md#renew-token)
* [Revoke Token](../../doc/controllers/o-auth.md#revoke-token)
* [Obtain Token](../../doc/controllers/o-auth.md#obtain-token)


# Renew Token

`RenewToken` is deprecated. For information about refreshing OAuth access tokens, see
[Migrate from Renew to Refresh OAuth Tokens](https://developer.squareup.com/docs/oauth-api/migrate-to-refresh-tokens).

Renews an OAuth access token before it expires.

OAuth access tokens besides your application's personal access token expire after __30 days__.
You can also renew expired tokens within __15 days__ of their expiration.
You cannot renew an access token that has been expired for more than 15 days.
Instead, the associated user must re-complete the OAuth flow from the beginning.

__Important:__ The `Authorization` header for this endpoint must have the
following format:

```
Authorization: Client APPLICATION_SECRET
```

Replace `APPLICATION_SECRET` with the application secret on the Credentials
page in the [developer dashboard](https://developer.squareup.com/apps).

```php
function renewToken(string $clientId, RenewTokenRequest $body): RenewTokenResponse
```

## Authentication

This endpoint requires [oauth2ClientSecret](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `clientId` | `string` | Template, Required | Your application ID, available from the [developer dashboard](https://developer.squareup.com/apps). |
| `body` | [`RenewTokenRequest`](../../doc/models/renew-token-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Response Type

**200**: Success

[`RenewTokenResponse`](../../doc/models/renew-token-response.md)

## Example Usage

```php
$clientId = 'client_id8';

$body = RenewTokenRequestBuilder::init()->build();

$oAuthController = $client->getOAuthController();

try {
    $result = $oAuthController->renewToken(
        $clientId,
        $body
    );
    echo 'RenewTokenResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Revoke Token

Revokes an access token generated with the OAuth flow.

If an account has more than one OAuth access token for your application, this
endpoint revokes all of them, regardless of which token you specify. When an
OAuth access token is revoked, all of the active subscriptions associated
with that OAuth token are canceled immediately.

__Important:__ The `Authorization` header for this endpoint must have the
following format:

```
Authorization: Client APPLICATION_SECRET
```

Replace `APPLICATION_SECRET` with the application secret on the OAuth
page in the [developer dashboard](https://developer.squareup.com/apps).

```php
function revokeToken(RevokeTokenRequest $body): RevokeTokenResponse
```

## Authentication

This endpoint requires [oauth2ClientSecret](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`RevokeTokenRequest`](../../doc/models/revoke-token-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Response Type

**200**: Success

[`RevokeTokenResponse`](../../doc/models/revoke-token-response.md)

## Example Usage

```php
$body = RevokeTokenRequestBuilder::init()->build();

$oAuthController = $client->getOAuthController();

try {
    $result = $oAuthController->revokeToken($body);
    echo 'RevokeTokenResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Obtain Token

Returns an OAuth access token.

The endpoint supports distinct methods of obtaining OAuth access tokens.
Applications specify a method by adding the `grant_type` parameter
in the request and also provide relevant information.

__Note:__ Regardless of the method application specified,
the endpoint always returns two items; an OAuth access token and
a refresh token in the response.

__OAuth tokens should only live on secure servers. Application clients
should never interact directly with OAuth tokens__.

:information_source: **Note** This endpoint does not require authentication.

```php
function obtainToken(ObtainTokenRequest $body): ObtainTokenResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`ObtainTokenRequest`](../../doc/models/obtain-token-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Response Type

**200**: Success

[`ObtainTokenResponse`](../../doc/models/obtain-token-response.md)

## Example Usage

```php
$body = ObtainTokenRequestBuilder::init(
    'client_id8',
    'client_secret4',
    'grant_type8'
)->build();

$oAuthController = $client->getOAuthController();

try {
    $result = $oAuthController->obtainToken($body);
    echo 'ObtainTokenResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

