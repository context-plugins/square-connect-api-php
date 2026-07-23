
# Retrieve Dispute Response

Defines fields in a `RetrieveDispute` response.

## Structure

`RetrieveDisputeResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `dispute` | [`?Dispute`](../../doc/models/dispute.md) | Optional | Represents a dispute a cardholder initiated with their bank. | getDispute(): ?Dispute | setDispute(?Dispute dispute): void |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Information about errors encountered during the request. | getErrors(): ?array | setErrors(?array errors): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\RetrieveDisputeResponseBuilder;
use SquareConnectAPILib\Models\Builders\DisputeBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;

$retrieveDisputeResponse = RetrieveDisputeResponseBuilder::init()
    ->dispute(
        DisputeBuilder::init()
            ->amountMoney(
                MoneyBuilder::init()
                    ->amount(2000)
                    ->currency('USD')
                    ->build()
            )
            ->brandDisputeId('100000282394')
            ->cardBrand('VISA')
            ->createdAt('2018-10-18T15:59:13.613Z')
            ->disputeId('dispute_id8')
            ->dueAt('2018-11-01T00:00:00.000Z')
            ->id('XDgyFu7yo1E2S5lQGGpYn')
            ->reason('NO_KNOWLEDGE')
            ->state('LOST')
            ->updatedAt('2018-10-18T15:59:13.613Z')
            ->build()
    )
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
    ->build();
```

