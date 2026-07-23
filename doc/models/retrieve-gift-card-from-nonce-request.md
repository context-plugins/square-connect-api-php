
# Retrieve Gift Card from Nonce Request

A request to retrieve gift cards by using nonces.

## Structure

`RetrieveGiftCardFromNonceRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `nonce` | `string` | Required | The nonce of the gift card to retrieve.<br><br>**Constraints**: *Minimum Length*: `1` | getNonce(): string | setNonce(string nonce): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\RetrieveGiftCardFromNonceRequestBuilder;

$retrieveGiftCardFromNonceRequest = RetrieveGiftCardFromNonceRequestBuilder::init(
    'nonce8'
)->build();
```

