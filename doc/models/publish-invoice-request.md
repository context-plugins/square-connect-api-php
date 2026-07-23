
# Publish Invoice Request

Describes a `PublishInvoice` request.

## Structure

`PublishInvoiceRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `idempotencyKey` | `?string` | Optional | A unique string that identifies the `PublishInvoice` request. If you do not<br>provide `idempotency_key` (or provide an empty string as the value), the endpoint<br>treats each request as independent.<br><br>For more information, see [Idempotency](https://developer.squareup.com/docs/working-with-apis/idempotency).<br><br>**Constraints**: *Maximum Length*: `128` | getIdempotencyKey(): ?string | setIdempotencyKey(?string idempotencyKey): void |
| `version` | `int` | Required | The version of the [invoice](https://developer.squareup.com/reference/square_2021-08-18/objects/Invoice) to publish.<br>This must match the current version of the invoice; otherwise, the request is rejected. | getVersion(): int | setVersion(int version): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\PublishInvoiceRequestBuilder;

$publishInvoiceRequest = PublishInvoiceRequestBuilder::init(
    140
)
    ->idempotencyKey('idempotency_key4')
    ->build();
```

