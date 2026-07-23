
# Order Fulfillment Pickup Details

Contains details necessary to fulfill a pickup order.

## Structure

`OrderFulfillmentPickupDetails`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `acceptedAt` | `?string` | Optional | The [timestamp](https://developer.squareup.com/docs/build-basics/working-with-dates)<br>indicating when the fulfillment was accepted. The timestamp must be in RFC 3339 format<br>(for example, "2016-09-04T23:59:33.123Z"). | getAcceptedAt(): ?string | setAcceptedAt(?string acceptedAt): void |
| `autoCompleteDuration` | `?string` | Optional | The duration of time after which an open and accepted pickup fulfillment<br>is automatically moved to the `COMPLETED` state. The duration must be in RFC 3339<br>format (for example, "P1W3D").<br><br>If not set, this pickup fulfillment remains accepted until it is canceled or completed. | getAutoCompleteDuration(): ?string | setAutoCompleteDuration(?string autoCompleteDuration): void |
| `cancelReason` | `?string` | Optional | A description of why the pickup was canceled. The maximum length: 100 characters.<br><br>**Constraints**: *Maximum Length*: `100` | getCancelReason(): ?string | setCancelReason(?string cancelReason): void |
| `canceledAt` | `?string` | Optional | The [timestamp](https://developer.squareup.com/docs/build-basics/working-with-dates)<br>indicating when the fulfillment was canceled. The timestamp must be in RFC 3339 format<br>(for example, "2016-09-04T23:59:33.123Z"). | getCanceledAt(): ?string | setCanceledAt(?string canceledAt): void |
| `curbsidePickupDetails` | [`?OrderFulfillmentPickupDetailsCurbsidePickupDetails`](../../doc/models/order-fulfillment-pickup-details-curbside-pickup-details.md) | Optional | Specific details for curbside pickup. | getCurbsidePickupDetails(): ?OrderFulfillmentPickupDetailsCurbsidePickupDetails | setCurbsidePickupDetails(?OrderFulfillmentPickupDetailsCurbsidePickupDetails curbsidePickupDetails): void |
| `expiredAt` | `?string` | Optional | The [timestamp](https://developer.squareup.com/docs/build-basics/working-with-dates)<br>indicating when the fulfillment expired. The timestamp must be in RFC 3339 format<br>(for example, "2016-09-04T23:59:33.123Z"). | getExpiredAt(): ?string | setExpiredAt(?string expiredAt): void |
| `expiresAt` | `?string` | Optional | The [timestamp](https://developer.squareup.com/docs/build-basics/working-with-dates)<br>indicating when this fulfillment expires if it is not accepted. The timestamp must be in RFC 3339 format<br>(for example, "2016-09-04T23:59:33.123Z"). The expiration time can only be set up to 7 days in the future.<br>If `expires_at` is not set, this pickup fulfillment is automatically accepted when<br>placed. | getExpiresAt(): ?string | setExpiresAt(?string expiresAt): void |
| `isCurbsidePickup` | `?bool` | Optional | If set to `true`, indicates that this pickup order is for curbside pickup, not in-store pickup. | getIsCurbsidePickup(): ?bool | setIsCurbsidePickup(?bool isCurbsidePickup): void |
| `note` | `?string` | Optional | A note meant to provide additional instructions about the pickup<br>fulfillment displayed in the Square Point of Sale application and set by the API.<br><br>**Constraints**: *Maximum Length*: `500` | getNote(): ?string | setNote(?string note): void |
| `pickedUpAt` | `?string` | Optional | The [timestamp](https://developer.squareup.com/docs/build-basics/working-with-dates)<br>indicating when the fulfillment was picked up by the recipient. The timestamp must be in RFC 3339 format<br>(for example, "2016-09-04T23:59:33.123Z"). | getPickedUpAt(): ?string | setPickedUpAt(?string pickedUpAt): void |
| `pickupAt` | `?string` | Optional | The [timestamp](https://developer.squareup.com/docs/build-basics/working-with-dates)<br>that represents the start of the pickup window. Must be in RFC 3339 timestamp format, e.g.,<br>"2016-09-04T23:59:33.123Z".<br><br>For fulfillments with the schedule type `ASAP`, this is automatically set<br>to the current time plus the expected duration to prepare the fulfillment. | getPickupAt(): ?string | setPickupAt(?string pickupAt): void |
| `pickupWindowDuration` | `?string` | Optional | The window of time in which the order should be picked up after the `pickup_at` timestamp.<br>Must be in RFC 3339 duration format, e.g., "P1W3D". Can be used as an<br>informational guideline for merchants. | getPickupWindowDuration(): ?string | setPickupWindowDuration(?string pickupWindowDuration): void |
| `placedAt` | `?string` | Optional | The [timestamp](https://developer.squareup.com/docs/build-basics/working-with-dates)<br>indicating when the fulfillment was placed. The timestamp must be in RFC 3339 format<br>(for example, "2016-09-04T23:59:33.123Z"). | getPlacedAt(): ?string | setPlacedAt(?string placedAt): void |
| `prepTimeDuration` | `?string` | Optional | The duration of time it takes to prepare this fulfillment.<br>The duration must be in RFC 3339 format (for example, "P1W3D"). | getPrepTimeDuration(): ?string | setPrepTimeDuration(?string prepTimeDuration): void |
| `readyAt` | `?string` | Optional | The [timestamp](https://developer.squareup.com/docs/build-basics/working-with-dates)<br>indicating when the fulfillment is marked as ready for pickup. The timestamp must be in RFC 3339 format<br>(for example, "2016-09-04T23:59:33.123Z"). | getReadyAt(): ?string | setReadyAt(?string readyAt): void |
| `recipient` | [`?OrderFulfillmentRecipient`](../../doc/models/order-fulfillment-recipient.md) | Optional | Contains information about the recipient of a fulfillment. | getRecipient(): ?OrderFulfillmentRecipient | setRecipient(?OrderFulfillmentRecipient recipient): void |
| `rejectedAt` | `?string` | Optional | The [timestamp](https://developer.squareup.com/docs/build-basics/working-with-dates)<br>indicating when the fulfillment was rejected. The timestamp must be in RFC 3339 format<br>(for example, "2016-09-04T23:59:33.123Z"). | getRejectedAt(): ?string | setRejectedAt(?string rejectedAt): void |
| `scheduleType` | `?string` | Optional | The schedule type of the pickup fulfillment. Defaults to `SCHEDULED`. | getScheduleType(): ?string | setScheduleType(?string scheduleType): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\OrderFulfillmentPickupDetailsBuilder;
use SquareConnectAPILib\Models\Builders\OrderFulfillmentPickupDetailsCurbsidePickupDetailsBuilder;

$orderFulfillmentPickupDetails = OrderFulfillmentPickupDetailsBuilder::init()
    ->acceptedAt('accepted_at4')
    ->autoCompleteDuration('auto_complete_duration6')
    ->cancelReason('cancel_reason2')
    ->canceledAt('canceled_at2')
    ->curbsidePickupDetails(
        OrderFulfillmentPickupDetailsCurbsidePickupDetailsBuilder::init()
            ->buyerArrivedAt('buyer_arrived_at8')
            ->curbsideDetails('curbside_details2')
            ->build()
    )
    ->build();
```

