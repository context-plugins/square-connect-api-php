
# Dispute Evidence

## Structure

`DisputeEvidence`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `disputeId` | `?string` | Optional | The ID of the dispute the evidence is associated with.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `40` | getDisputeId(): ?string | setDisputeId(?string disputeId): void |
| `evidenceFile` | [`?DisputeEvidenceFile`](../../doc/models/dispute-evidence-file.md) | Optional | A file to be uploaded as dispute evidence. | getEvidenceFile(): ?DisputeEvidenceFile | setEvidenceFile(?DisputeEvidenceFile evidenceFile): void |
| `evidenceId` | `?string` | Optional | The Square-generated ID of the evidence.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `40` | getEvidenceId(): ?string | setEvidenceId(?string evidenceId): void |
| `evidenceText` | `?string` | Optional | Raw text<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `500` | getEvidenceText(): ?string | setEvidenceText(?string evidenceText): void |
| `evidenceType` | `?string` | Optional | The type of the evidence. | getEvidenceType(): ?string | setEvidenceType(?string evidenceType): void |
| `id` | `?string` | Optional | The Square-generated ID of the evidence.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `40` | getId(): ?string | setId(?string id): void |
| `uploadedAt` | `?string` | Optional | The time when the next action is due, in RFC 3339 format.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `40` | getUploadedAt(): ?string | setUploadedAt(?string uploadedAt): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\DisputeEvidenceBuilder;
use SquareConnectAPILib\Models\Builders\DisputeEvidenceFileBuilder;

$disputeEvidence = DisputeEvidenceBuilder::init()
    ->disputeId('dispute_id6')
    ->evidenceFile(
        DisputeEvidenceFileBuilder::init()
            ->filename('filename8')
            ->filetype('filetype8')
            ->build()
    )
    ->evidenceId('evidence_id2')
    ->evidenceText('evidence_text8')
    ->evidenceType('evidence_type0')
    ->build();
```

