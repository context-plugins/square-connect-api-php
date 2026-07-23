
# List Refunds Response

Defines the fields that are included in the response body of
a request to the [ListRefunds](https://developer.squareup.com/reference/square_2021-08-18/transactions-api/list-refunds) endpoint.

One of `errors` or `refunds` is present in a given response (never both).

## Structure

`ListRefundsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cursor` | `?string` | Optional | A pagination cursor for retrieving the next set of results,<br>if any remain. Provide this value as the `cursor` parameter in a subsequent<br>request to this endpoint.<br><br>See [Paginating results](https://developer.squareup.com/docs/working-with-apis/pagination) for more information. | getCursor(): ?string | setCursor(?string cursor): void |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `refunds` | [`?(Refund[])`](../../doc/models/refund.md) | Optional | An array of refunds that match your query. | getRefunds(): ?array | setRefunds(?array refunds): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\ListRefundsResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\RefundBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;
use SquareConnectAPILib\Models\Builders\AdditionalRecipientBuilder;

$listRefundsResponse = ListRefundsResponseBuilder::init()
    ->cursor('cursor0')
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
                ->build()
        ]
    )
    ->refunds(
        [
            RefundBuilder::init(
                MoneyBuilder::init()
                    ->amount(100)
                    ->currency('USD')
                    ->build(),
                'b27436d1-7f8e-5610-45c6-417ef71434b4-SW',
                '18YC4JDH91E1H',
                'some reason',
                'APPROVED',
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
                            ->receivableId('receivable_id6')
                            ->build()
                    ]
                )
                ->createdAt('2016-01-20T00:28:18Z')
                ->processingFeeMoney(
                    MoneyBuilder::init()
                        ->amount(112)
                        ->currency('currency8')
                        ->build()
                )
                ->build()
        ]
    )
    ->build();
```

