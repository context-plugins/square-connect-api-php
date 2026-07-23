
# V1 Create Refund Request

V1CreateRefundRequest

## Structure

`V1CreateRefundRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `paymentId` | `string` | Required | The ID of the payment to refund. If you are creating a `PARTIAL`<br>refund for a split tender payment, instead provide the id of the<br>particular tender you want to refund. | getPaymentId(): string | setPaymentId(string paymentId): void |
| `reason` | `string` | Required | The reason for the refund. | getReason(): string | setReason(string reason): void |
| `refundedMoney` | [`?V1Money`](../../doc/models/v1-money.md) | Optional | - | getRefundedMoney(): ?V1Money | setRefundedMoney(?V1Money refundedMoney): void |
| `requestIdempotenceKey` | `?string` | Optional | An optional key to ensure idempotence if you issue the same PARTIAL refund request more than once. | getRequestIdempotenceKey(): ?string | setRequestIdempotenceKey(?string requestIdempotenceKey): void |
| `type` | `string` | Required | The type of refund (FULL or PARTIAL). | getType(): string | setType(string type): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\V1CreateRefundRequestBuilder;
use SquareConnectAPILib\Models\Builders\V1MoneyBuilder;

$v1CreateRefundRequest = V1CreateRefundRequestBuilder::init(
    'payment_id4',
    'reason0',
    'type6'
)
    ->refundedMoney(
        V1MoneyBuilder::init()
            ->amount(214)
            ->currencyCode('currency_code2')
            ->build()
    )
    ->requestIdempotenceKey('request_idempotence_key4')
    ->build();
```

