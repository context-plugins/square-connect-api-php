
# Get Payment Refund Response

Defines the response returned by [GetRefund](https://developer.squareup.com/reference/square_2021-08-18/refunds-api/get-payment-refund).

Note: If there are errors processing the request, the refund field might not be
present or it might be present in a FAILED state.

## Structure

`GetPaymentRefundResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Information about errors encountered during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `refund` | [`?PaymentRefund`](../../doc/models/payment-refund.md) | Optional | Represents a refund of a payment made using Square. Contains information about<br>the original payment and the amount of money refunded. | getRefund(): ?PaymentRefund | setRefund(?PaymentRefund refund): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\GetPaymentRefundResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\PaymentRefundBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;
use SquareConnectAPILib\Models\Builders\ProcessingFeeBuilder;

$getPaymentRefundResponse = GetPaymentRefundResponseBuilder::init()
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
                ->amount(1000)
                ->currency('USD')
                ->build(),
            'O2QAAhTYs7rUfzlxT38GMO7LvaB_q7JwCHtxmgXrh8fAhV468WQ44VxDtL7CU4yVRlsbXmI'
        )
            ->appFeeMoney(
                MoneyBuilder::init()
                    ->amount(106)
                    ->currency('currency4')
                    ->build()
            )
            ->createdAt('2019-07-06T18:01:22.123Z')
            ->locationId('XK3DBG77NJBFX')
            ->orderId('2duiyoqbfeXY0DBi15GEyk5Epa4F')
            ->paymentId('O2QAAhTYs7rUfzlxT38GMO7LvaB')
            ->processingFee(
                [
                    ProcessingFeeBuilder::init()
                        ->amountMoney(
                            MoneyBuilder::init()
                                ->amount(-59)
                                ->currency('USD')
                                ->build()
                        )
                        ->effectiveAt('2019-07-06T20:01:12.000Z')
                        ->type('INITIAL')
                        ->build()
                ]
            )
            ->status('COMPLETED')
            ->updatedAt('2019-07-06T18:06:03.874Z')
            ->build()
    )
    ->build();
```

