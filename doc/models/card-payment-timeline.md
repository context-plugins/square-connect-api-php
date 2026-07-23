
# Card Payment Timeline

The timeline for card payments.

## Structure

`CardPaymentTimeline`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `authorizedAt` | `?string` | Optional | The timestamp when the payment was authorized, in RFC 3339 format. | getAuthorizedAt(): ?string | setAuthorizedAt(?string authorizedAt): void |
| `capturedAt` | `?string` | Optional | The timestamp when the payment was captured, in RFC 3339 format. | getCapturedAt(): ?string | setCapturedAt(?string capturedAt): void |
| `voidedAt` | `?string` | Optional | The timestamp when the payment was voided, in RFC 3339 format. | getVoidedAt(): ?string | setVoidedAt(?string voidedAt): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CardPaymentTimelineBuilder;

$cardPaymentTimeline = CardPaymentTimelineBuilder::init()
    ->authorizedAt('authorized_at8')
    ->capturedAt('captured_at8')
    ->voidedAt('voided_at2')
    ->build();
```

