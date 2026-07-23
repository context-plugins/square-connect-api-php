
# Submit Evidence Response

Defines the fields in a `SubmitEvidence` response.

## Structure

`SubmitEvidenceResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `dispute` | [`?Dispute`](../../doc/models/dispute.md) | Optional | Represents a dispute a cardholder initiated with their bank. | getDispute(): ?Dispute | setDispute(?Dispute dispute): void |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Information about errors encountered during the request. | getErrors(): ?array | setErrors(?array errors): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\SubmitEvidenceResponseBuilder;
use SquareConnectAPILib\Models\Builders\DisputeBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;

$submitEvidenceResponse = SubmitEvidenceResponseBuilder::init()
    ->dispute(
        DisputeBuilder::init()
            ->amountMoney(
                MoneyBuilder::init()
                    ->amount(2000)
                    ->currency('USD')
                    ->build()
            )
            ->brandDisputeId('100000399240')
            ->cardBrand('VISA')
            ->createdAt('2018-10-18T16:02:15.313Z')
            ->disputeId('dispute_id8')
            ->dueAt('2018-11-01T00:00:00.000Z')
            ->id('EAZoK70gX3fyvibecLwIGB')
            ->reason('NO_KNOWLEDGE')
            ->state('PROCESSING')
            ->updatedAt('2018-10-18T16:02:15.313Z')
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
                ->build()
        ]
    )
    ->build();
```

