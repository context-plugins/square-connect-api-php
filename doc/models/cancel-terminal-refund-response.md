
# Cancel Terminal Refund Response

## Structure

`CancelTerminalRefundResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Information about errors encountered during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `refund` | [`?TerminalRefund`](../../doc/models/terminal-refund.md) | Optional | - | getRefund(): ?TerminalRefund | setRefund(?TerminalRefund refund): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CancelTerminalRefundResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\TerminalRefundBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;

$cancelTerminalRefundResponse = CancelTerminalRefundResponseBuilder::init()
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
    ->refund(
        TerminalRefundBuilder::init(
            MoneyBuilder::init()
                ->amount(100)
                ->currency('CAD')
                ->build(),
            '5O5OvgkcNUhl7JBuINflcjKqUzXZY'
        )
            ->appId('sandbox-sq0idb-c2OuYt13YaCAeJq_2cd8OQ')
            ->cancelReason('SELLER_CANCELED')
            ->createdAt('2020-10-21T22:47:23.241Z')
            ->deadlineDuration('PT5M')
            ->deviceId('42690809-faa2-4701-a24b-19d3d34c9aaa')
            ->id('g6ycb6HD-5O5OvgkcNUhl7JBuINflcjKqUzXZY')
            ->locationId('76C9W6K8CNNQ5')
            ->orderId('kcuKDKreRaI4gF4TjmEgZjHk8Z7YY')
            ->reason('reason')
            ->status('CANCELED')
            ->updatedAt('2020-10-21T22:47:30.096Z')
            ->build()
    )
    ->build();
```

