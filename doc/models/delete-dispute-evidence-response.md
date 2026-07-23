
# Delete Dispute Evidence Response

Defines the fields in a `DeleteDisputeEvidence` response.

## Structure

`DeleteDisputeEvidenceResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Information about errors encountered during the request. | getErrors(): ?array | setErrors(?array errors): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\DeleteDisputeEvidenceResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;

$deleteDisputeEvidenceResponse = DeleteDisputeEvidenceResponseBuilder::init()
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

