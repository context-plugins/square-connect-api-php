
# Deprecated Create Dispute Evidence File Request

Defines the parameters for a `DeprecatedCreateDisputeEvidenceFile` request.

## Structure

`DeprecatedCreateDisputeEvidenceFileRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `contentType` | `?string` | Optional | The MIME type of the uploaded file.<br>The type can be image/heic, image/heif, image/jpeg, application/pdf, image/png, or image/tiff.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `40` | getContentType(): ?string | setContentType(?string contentType): void |
| `evidenceType` | `?string` | Optional | The type of evidence you are uploading. | getEvidenceType(): ?string | setEvidenceType(?string evidenceType): void |
| `idempotencyKey` | `string` | Required | The Unique ID. For more information, see [Idempotency](https://developer.squareup.com/docs/working-with-apis/idempotency).<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `45` | getIdempotencyKey(): string | setIdempotencyKey(string idempotencyKey): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\DeprecatedCreateDisputeEvidenceFileRequestBuilder;

$deprecatedCreateDisputeEvidenceFileRequest = DeprecatedCreateDisputeEvidenceFileRequestBuilder::init(
    'idempotency_key4'
)
    ->contentType('content_type2')
    ->evidenceType('evidence_type4')
    ->build();
```

