
# Deprecated Create Dispute Evidence File Response

Defines the fields in a `DeprecatedCreateDisputeEvidenceFile` response.

## Structure

`DeprecatedCreateDisputeEvidenceFileResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `evidence` | [`?DisputeEvidence`](../../doc/models/dispute-evidence.md) | Optional | - | getEvidence(): ?DisputeEvidence | setEvidence(?DisputeEvidence evidence): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\DeprecatedCreateDisputeEvidenceFileResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\DisputeEvidenceBuilder;
use SquareConnectAPILib\Models\Builders\DisputeEvidenceFileBuilder;

$deprecatedCreateDisputeEvidenceFileResponse = DeprecatedCreateDisputeEvidenceFileResponseBuilder::init()
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
    ->evidence(
        DisputeEvidenceBuilder::init()
            ->disputeId('bVTprrwk0gygTLZ96VX1oB')
            ->evidenceFile(
                DisputeEvidenceFileBuilder::init()
                    ->filename('evidence.tiff')
                    ->filetype('image/tiff')
                    ->build()
            )
            ->evidenceId('TOomLInj6iWmP3N8qfCXrB')
            ->evidenceText('evidence_text6')
            ->evidenceType('GENERIC_EVIDENCE')
            ->uploadedAt('2018-10-18T16:01:10.000Z')
            ->build()
    )
    ->build();
```

