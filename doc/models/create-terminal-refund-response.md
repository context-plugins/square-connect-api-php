
# Create Terminal Refund Response

## Structure

`CreateTerminalRefundResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Information about errors encountered during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `refund` | [`?TerminalRefund`](../../doc/models/terminal-refund.md) | Optional | - | getRefund(): ?TerminalRefund | setRefund(?TerminalRefund refund): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CreateTerminalRefundResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\TerminalRefundBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;

$createTerminalRefundResponse = CreateTerminalRefundResponseBuilder::init()
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
            ->reason('Returning items')
            ->status('PENDING')
            ->updatedAt('2020-09-29T15:21:46.771Z')
            ->build()
    )
    ->build();
```

