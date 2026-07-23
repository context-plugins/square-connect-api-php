
# Cancel Payment by Idempotency Key Request

Describes a request to cancel a payment using
[CancelPaymentByIdempotencyKey](https://developer.squareup.com/reference/square_2021-08-18/payments-api/cancel-payment-by-idempotency-key).

## Structure

`CancelPaymentByIdempotencyKeyRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `idempotencyKey` | `string` | Required | The `idempotency_key` identifying the payment to be canceled.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `45` | getIdempotencyKey(): string | setIdempotencyKey(string idempotencyKey): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CancelPaymentByIdempotencyKeyRequestBuilder;

$cancelPaymentByIdempotencyKeyRequest = CancelPaymentByIdempotencyKeyRequestBuilder::init(
    'idempotency_key2'
)->build();
```

