
# Deprecated Create Dispute Evidence Text Response

Defines the fields in a `DeprecatedCreateDisputeEvidenceText` response.

## Structure

`DeprecatedCreateDisputeEvidenceTextResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `evidence` | [`?DisputeEvidence`](../../doc/models/dispute-evidence.md) | Optional | - | getEvidence(): ?DisputeEvidence | setEvidence(?DisputeEvidence evidence): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\DeprecatedCreateDisputeEvidenceTextResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\DisputeEvidenceBuilder;
use SquareConnectAPILib\Models\Builders\DisputeEvidenceFileBuilder;

$deprecatedCreateDisputeEvidenceTextResponse = DeprecatedCreateDisputeEvidenceTextResponseBuilder::init()
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
    ->evidence(
        DisputeEvidenceBuilder::init()
            ->disputeId('bVTprrwk0gygTLZ96VX1oB')
            ->evidenceFile(
                DisputeEvidenceFileBuilder::init()
                    ->filename('filename8')
                    ->filetype('filetype8')
                    ->build()
            )
            ->evidenceId('evidence_id0')
            ->evidenceText('1Z8888888888888888')
            ->evidenceType('TRACKING_NUMBER')
            ->id('TOomLInj6iWmP3N8qfCXrB')
            ->uploadedAt('2018-10-18T16:01:10.000Z')
            ->build()
    )
    ->build();
```

