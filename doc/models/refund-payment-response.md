
# Refund Payment Response

Defines the response returned by
[RefundPayment](https://developer.squareup.com/reference/square_2021-08-18/refunds-api/refund-payment).

If there are errors processing the request, the `refund` field might not be
present, or it might be present with a status of `FAILED`.

## Structure

`RefundPaymentResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Information about errors encountered during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `refund` | [`?PaymentRefund`](../../doc/models/payment-refund.md) | Optional | Represents a refund of a payment made using Square. Contains information about<br>the original payment and the amount of money refunded. | getRefund(): ?PaymentRefund | setRefund(?PaymentRefund refund): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\RefundPaymentResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\PaymentRefundBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;

$refundPaymentResponse = RefundPaymentResponseBuilder::init()
    ->errors(
        [
            ErrorBuilder::init(
                'category8',
                'code8'
            )
                ->detail('detail6')
                ->field('field4')
                ->build()
        ]
    )
    ->refund(
        PaymentRefundBuilder::init(
            MoneyBuilder::init()
                ->amount(100)
                ->currency('USD')
                ->build(),
            'UNOE3kv2BZwqHlJ830RCt5YCuaB_xVteEWVFkXDvKN1ddidfJWipt8p9whmElKT5mZtJ7wZ'
        )
            ->appFeeMoney(
                MoneyBuilder::init()
                    ->amount(106)
                    ->currency('currency4')
                    ->build()
            )
            ->createdAt('2018-10-17T20:41:55.520Z')
            ->locationId('location_id2')
            ->orderId('order_id2')
            ->paymentId('UNOE3kv2BZwqHlJ830RCt5YCuaB')
            ->status('PENDING')
            ->updatedAt('2018-10-17T20:41:55.520Z')
            ->build()
    )
    ->build();
```

