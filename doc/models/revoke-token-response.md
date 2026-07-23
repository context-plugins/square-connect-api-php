
# Revoke Token Response

## Structure

`RevokeTokenResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `success` | `?bool` | Optional | If the request is successful, this is true. | getSuccess(): ?bool | setSuccess(?bool success): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\RevokeTokenResponseBuilder;

$revokeTokenResponse = RevokeTokenResponseBuilder::init()
    ->success(true)
    ->build();
```

