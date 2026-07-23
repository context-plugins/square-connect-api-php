
# List Dispute Evidence Response

Defines the fields in a `ListDisputeEvidence` response.

## Structure

`ListDisputeEvidenceResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cursor` | `?string` | Optional | The pagination cursor to be used in a subsequent request.<br>If unset, this is the final response. For more information, see [Pagination](https://developer.squareup.com/docs/basics/api101/pagination). | getCursor(): ?string | setCursor(?string cursor): void |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Information about errors encountered during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `evidence` | [`?(DisputeEvidence[])`](../../doc/models/dispute-evidence.md) | Optional | The list of evidence previously uploaded to the specified dispute. | getEvidence(): ?array | setEvidence(?array evidence): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\ListDisputeEvidenceResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\DisputeEvidenceBuilder;
use SquareConnectAPILib\Models\Builders\DisputeEvidenceFileBuilder;

$listDisputeEvidenceResponse = ListDisputeEvidenceResponseBuilder::init()
    ->cursor('G1aSTRm48CLjJsg6Sg3hQN1b1OMaoVuG')
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
    ->evidence(
        [
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
                ->build(),
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
        ]
    )
    ->build();
```

