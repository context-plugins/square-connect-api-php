
# Renew Token Request

## Structure

`RenewTokenRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accessToken` | `?string` | Optional | The token you want to renew.<br><br>**Constraints**: *Minimum Length*: `2`, *Maximum Length*: `1024` | getAccessToken(): ?string | setAccessToken(?string accessToken): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\RenewTokenRequestBuilder;

$renewTokenRequest = RenewTokenRequestBuilder::init()
    ->accessToken('access_token2')
    ->build();
```

