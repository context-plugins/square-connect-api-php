
# V1 Update Order Request

V1UpdateOrderRequest

## Structure

`V1UpdateOrderRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `action` | `string` | Required | The action to perform on the order (COMPLETE, CANCEL, or REFUND). | getAction(): string | setAction(string action): void |
| `canceledNote` | `?string` | Optional | A merchant-specified note about the canceling of the order. Only valid if action is CANCEL. | getCanceledNote(): ?string | setCanceledNote(?string canceledNote): void |
| `completedNote` | `?string` | Optional | A merchant-specified note about the completion of the order. Only valid if action is COMPLETE. | getCompletedNote(): ?string | setCompletedNote(?string completedNote): void |
| `refundedNote` | `?string` | Optional | A merchant-specified note about the refunding of the order. Only valid if action is REFUND. | getRefundedNote(): ?string | setRefundedNote(?string refundedNote): void |
| `shippedTrackingNumber` | `?string` | Optional | The tracking number of the shipment associated with the order. Only valid if action is COMPLETE. | getShippedTrackingNumber(): ?string | setShippedTrackingNumber(?string shippedTrackingNumber): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\V1UpdateOrderRequestBuilder;

$v1UpdateOrderRequest = V1UpdateOrderRequestBuilder::init(
    'action4'
)
    ->canceledNote('canceled_note2')
    ->completedNote('completed_note8')
    ->refundedNote('refunded_note2')
    ->shippedTrackingNumber('shipped_tracking_number8')
    ->build();
```

