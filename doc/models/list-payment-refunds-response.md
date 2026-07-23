
# List Payment Refunds Response

Defines the response returned by [ListPaymentRefunds](https://developer.squareup.com/reference/square_2021-08-18/refunds-api/list-payment-refunds).

Either `errors` or `refunds` is present in a given response (never both).

## Structure

`ListPaymentRefundsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cursor` | `?string` | Optional | The pagination cursor to be used in a subsequent request. If empty,<br>this is the final response.<br><br>For more information, see [Pagination](https://developer.squareup.com/docs/basics/api101/pagination). | getCursor(): ?string | setCursor(?string cursor): void |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Information about errors encountered during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `refunds` | [`?(PaymentRefund[])`](../../doc/models/payment-refund.md) | Optional | The list of requested refunds. | getRefunds(): ?array | setRefunds(?array refunds): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\ListPaymentRefundsResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\PaymentRefundBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;
use SquareConnectAPILib\Models\Builders\ProcessingFeeBuilder;

$listPaymentRefundsResponse = ListPaymentRefundsResponseBuilder::init()
    ->cursor('5evquW1YswHoT4EoyUhzMmTsCnsSXBU9U0WJ4FU4623nrMQcocH0RGU6Up1YkwfiMcF59ood58EBTEGgzMTGHQJpocic7ExOL0NtrTXCeWcv0UJIJNk8eXb')
    ->errors(
        [
            ErrorBuilder::init(
                'category8',
                'code8'
            )
                ->detail('detail6')
                ->field('field4')
                ->build(),
            ErrorBuilder::init(
                'category8',
                'code8'
            )
                ->detail('detail6')
                ->field('field4')
                ->build(),
            ErrorBuilder::init(
                'category8',
                'code8'
            )
                ->detail('detail6')
                ->field('field4')
                ->build()
        ]
    )
    ->refunds(
        [
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
                ->createdAt('2019-07-06T18:01:22.335Z')
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
                ->updatedAt('2019-07-06T18:06:04.653Z')
                ->build(),
            PaymentRefundBuilder::init(
                MoneyBuilder::init()
                    ->amount(1000)
                    ->currency('USD')
                    ->build(),
                '8TDIQvFw8PeDIxhSfd5yyX7GuaB_13px5Vrz01qzzuoGzmjsZIxDjfHhbkm2XppBUX1dW7I'
            )
                ->appFeeMoney(
                    MoneyBuilder::init()
                        ->amount(106)
                        ->currency('currency4')
                        ->build()
                )
                ->createdAt('2019-07-06T17:01:54.232Z')
                ->locationId('XK3DBG77NJBFX')
                ->orderId('w6EXfEwS03oTQsnZTCqfE6f67e4F')
                ->paymentId('8TDIQvFw8PeDIxhSfd5yyX7GuaB')
                ->processingFee(
                    [
                        ProcessingFeeBuilder::init()
                            ->amountMoney(
                                MoneyBuilder::init()
                                    ->amount(-59)
                                    ->currency('USD')
                                    ->build()
                            )
                            ->effectiveAt('2019-07-06T19:01:45.000Z')
                            ->type('INITIAL')
                            ->build()
                    ]
                )
                ->status('COMPLETED')
                ->updatedAt('2019-07-06T17:21:04.684Z')
                ->build()
        ]
    )
    ->build();
```

