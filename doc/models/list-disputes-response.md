
# List Disputes Response

Defines fields in a `ListDisputes` response.

## Structure

`ListDisputesResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cursor` | `?string` | Optional | The pagination cursor to be used in a subsequent request.<br>If unset, this is the final response. For more information, see [Pagination](https://developer.squareup.com/docs/basics/api101/pagination). | getCursor(): ?string | setCursor(?string cursor): void |
| `disputes` | [`?(Dispute[])`](../../doc/models/dispute.md) | Optional | The list of disputes. | getDisputes(): ?array | setDisputes(?array disputes): void |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Information about errors encountered during the request. | getErrors(): ?array | setErrors(?array errors): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\ListDisputesResponseBuilder;
use SquareConnectAPILib\Models\Builders\DisputeBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;

$listDisputesResponse = ListDisputesResponseBuilder::init()
    ->cursor('G1aSTRm48CLjJsg6Sg3hQN1b1OMaoVuG')
    ->disputes(
        [
            DisputeBuilder::init()
                ->amountMoney(
                    MoneyBuilder::init()
                        ->amount(1000)
                        ->currency('USD')
                        ->build()
                )
                ->brandDisputeId('100000809947')
                ->cardBrand('VISA')
                ->createdAt('2018-10-12T02:20:25.577Z')
                ->disputeId('dispute_id4')
                ->dueAt('2018-10-11T00:00:00.000Z')
                ->id('OnY1AZwhSi775rbNIK4gv')
                ->reason('NO_KNOWLEDGE')
                ->state('EVIDENCE_REQUIRED')
                ->updatedAt('2018-10-12T02:20:25.577Z')
                ->build()
        ]
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

