
# Refund Payment Request

Describes a request to refund a payment using [RefundPayment](https://developer.squareup.com/reference/square_2021-08-18/refunds-api/refund-payment).

## Structure

`RefundPaymentRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amountMoney` | [`Money`](../../doc/models/money.md) | Required | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getAmountMoney(): Money | setAmountMoney(Money amountMoney): void |
| `appFeeMoney` | [`?Money`](../../doc/models/money.md) | Optional | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getAppFeeMoney(): ?Money | setAppFeeMoney(?Money appFeeMoney): void |
| `idempotencyKey` | `string` | Required | A unique string that identifies this `RefundPayment` request. The key can be any valid string<br>but must be unique for every `RefundPayment` request.<br><br>For more information, see [Idempotency](https://developer.squareup.com/docs/working-with-apis/idempotency).<br><br>**Constraints**: *Minimum Length*: `1` | getIdempotencyKey(): string | setIdempotencyKey(string idempotencyKey): void |
| `paymentId` | `string` | Required | The unique ID of the payment being refunded.<br><br>**Constraints**: *Minimum Length*: `1` | getPaymentId(): string | setPaymentId(string paymentId): void |
| `reason` | `?string` | Optional | A description of the reason for the refund.<br><br>**Constraints**: *Maximum Length*: `192` | getReason(): ?string | setReason(?string reason): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\RefundPaymentRequestBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;

$refundPaymentRequest = RefundPaymentRequestBuilder::init(
    MoneyBuilder::init()
        ->amount(186)
        ->currency('currency8')
        ->build(),
    'idempotency_key8',
    'payment_id2'
)
    ->appFeeMoney(
        MoneyBuilder::init()
            ->amount(106)
            ->currency('currency4')
            ->build()
    )
    ->reason('reason8')
    ->build();
```

