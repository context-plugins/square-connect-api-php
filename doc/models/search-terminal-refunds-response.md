
# Search Terminal Refunds Response

## Structure

`SearchTerminalRefundsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cursor` | `?string` | Optional | The pagination cursor to be used in a subsequent request. If empty,<br>this is the final response.<br><br>See [Pagination](https://developer.squareup.com/docs/basics/api101/pagination) for more information. | getCursor(): ?string | setCursor(?string cursor): void |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Information about errors encountered during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `refunds` | [`?(TerminalRefund[])`](../../doc/models/terminal-refund.md) | Optional | The requested search result of `TerminalRefund` objects. | getRefunds(): ?array | setRefunds(?array refunds): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\SearchTerminalRefundsResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\TerminalRefundBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;

$searchTerminalRefundsResponse = SearchTerminalRefundsResponseBuilder::init()
    ->cursor('cursor8')
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
    ->refunds(
        [
            TerminalRefundBuilder::init(
                MoneyBuilder::init()
                    ->amount(111)
                    ->currency('CAD')
                    ->build(),
                '5O5OvgkcNUhl7JBuINflcjKqUzXZY'
            )
                ->appId('sandbox-sq0idb-c2OuYt13YaCAeJq_2cd8OQ')
                ->cancelReason('cancel_reason4')
                ->createdAt('2020-09-29T15:21:46.771Z')
                ->deadlineDuration('PT5M')
                ->deviceId('f72dfb8e-4d65-4e56-aade-ec3fb8d33291')
                ->id('009DP5HD-5O5OvgkcNUhl7JBuINflcjKqUzXZY')
                ->locationId('76C9W6K8CNNQ5')
                ->orderId('kcuKDKreRaI4gF4TjmEgZjHk8Z7YY')
                ->reason('Returning item')
                ->refundId('5O5OvgkcNUhl7JBuINflcjKqUzXZY_43Q4iGp7sNeATiWrUruA1EYeMRUXaddXXlDDJ1EQLvb')
                ->status('COMPLETED')
                ->updatedAt('2020-09-29T15:21:48.675Z')
                ->build()
        ]
    )
    ->build();
```

