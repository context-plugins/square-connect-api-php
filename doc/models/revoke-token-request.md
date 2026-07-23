
# Revoke Token Request

## Structure

`RevokeTokenRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accessToken` | `?string` | Optional | The access token of the merchant whose token you want to revoke.<br>Do not provide a value for merchant_id if you provide this parameter.<br><br>**Constraints**: *Minimum Length*: `2`, *Maximum Length*: `1024` | getAccessToken(): ?string | setAccessToken(?string accessToken): void |
| `clientId` | `?string` | Optional | The Square issued ID for your application, available from the<br>[developer dashboard](https://developer.squareup.com/apps).<br><br>**Constraints**: *Maximum Length*: `191` | getClientId(): ?string | setClientId(?string clientId): void |
| `merchantId` | `?string` | Optional | The ID of the merchant whose token you want to revoke.<br>Do not provide a value for access_token if you provide this parameter. | getMerchantId(): ?string | setMerchantId(?string merchantId): void |
| `revokeOnlyAccessToken` | `?bool` | Optional | If `true`, terminate the given single access token, but do not<br>terminate the entire authorization.<br>Default: `false` | getRevokeOnlyAccessToken(): ?bool | setRevokeOnlyAccessToken(?bool revokeOnlyAccessToken): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\RevokeTokenRequestBuilder;

$revokeTokenRequest = RevokeTokenRequestBuilder::init()
    ->accessToken('access_token8')
    ->clientId('client_id2')
    ->merchantId('merchant_id0')
    ->revokeOnlyAccessToken(false)
    ->build();
```

