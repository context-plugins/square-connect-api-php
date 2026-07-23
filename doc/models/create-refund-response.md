
# Create Refund Response

Defines the fields that are included in the response body of
a request to the [CreateRefund](https://developer.squareup.com/reference/square_2021-08-18/transactions-api/create-refund) endpoint.

One of `errors` or `refund` is present in a given response (never both).

## Structure

`CreateRefundResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `refund` | [`?Refund`](../../doc/models/refund.md) | Optional | Represents a refund processed for a Square transaction. | getRefund(): ?Refund | setRefund(?Refund refund): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CreateRefundResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\RefundBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;
use SquareConnectAPILib\Models\Builders\AdditionalRecipientBuilder;

$createRefundResponse = CreateRefundResponseBuilder::init()
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
        RefundBuilder::init(
            MoneyBuilder::init()
                ->amount(100)
                ->currency('USD')
                ->build(),
            'b27436d1-7f8e-5610-45c6-417ef71434b4-SW',
            '18YC4JDH91E1H',
            'some reason',
            'PENDING',
            'MtZRYYdDrYNQbOvV7nbuBvMF',
            'KnL67ZIwXCPtzOrqj0HrkxMF'
        )
            ->additionalRecipients(
                [
                    AdditionalRecipientBuilder::init(
                        MoneyBuilder::init()
                            ->amount(10)
                            ->currency('USD')
                            ->build(),
                        '057P5VYJ4A5X1'
                    )
                        ->description('Application fees')
                        ->receivableId('ISu5xwxJ5v0CMJTQq7RvqyMF')
                        ->build()
                ]
            )
            ->createdAt('2016-02-12T00:28:18Z')
            ->processingFeeMoney(
                MoneyBuilder::init()
                    ->amount(112)
                    ->currency('currency8')
                    ->build()
            )
            ->build()
    )
    ->build();
```

