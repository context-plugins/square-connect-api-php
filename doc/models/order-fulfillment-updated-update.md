
# Order Fulfillment Updated Update

Information about fulfillment updates.

## Structure

`OrderFulfillmentUpdatedUpdate`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `fulfillmentUid` | `?string` | Optional | A unique ID that identifies the fulfillment only within this order. | getFulfillmentUid(): ?string | setFulfillmentUid(?string fulfillmentUid): void |
| `newState` | `?string` | Optional | The state of the fulfillment after the change. The state might be equal to `old_state` if a non-state<br>field was changed on the fulfillment (such as the tracking number). | getNewState(): ?string | setNewState(?string newState): void |
| `oldState` | `?string` | Optional | The state of the fulfillment before the change.<br>The state is not populated if the fulfillment is created with this new `Order` version. | getOldState(): ?string | setOldState(?string oldState): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\OrderFulfillmentUpdatedUpdateBuilder;

$orderFulfillmentUpdatedUpdate = OrderFulfillmentUpdatedUpdateBuilder::init()
    ->fulfillmentUid('fulfillment_uid8')
    ->newState('new_state4')
    ->oldState('old_state4')
    ->build();
```

