
# Deprecated Create Dispute Evidence Text Request

Defines the parameters for a `DeprecatedCreateDisputeEvidenceText` request.

## Structure

`DeprecatedCreateDisputeEvidenceTextRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `evidenceText` | `string` | Required | The evidence string.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `500` | getEvidenceText(): string | setEvidenceText(string evidenceText): void |
| `evidenceType` | `?string` | Optional | The type of evidence you are uploading. | getEvidenceType(): ?string | setEvidenceType(?string evidenceType): void |
| `idempotencyKey` | `string` | Required | The Unique ID. For more information, see [Idempotency](https://developer.squareup.com/docs/working-with-apis/idempotency).<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `45` | getIdempotencyKey(): string | setIdempotencyKey(string idempotencyKey): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\DeprecatedCreateDisputeEvidenceTextRequestBuilder;

$deprecatedCreateDisputeEvidenceTextRequest = DeprecatedCreateDisputeEvidenceTextRequestBuilder::init(
    'evidence_text6',
    'idempotency_key8'
)
    ->evidenceType('evidence_type8')
    ->build();
```

