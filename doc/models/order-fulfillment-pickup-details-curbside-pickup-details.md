
# Order Fulfillment Pickup Details Curbside Pickup Details

Specific details for curbside pickup.

## Structure

`OrderFulfillmentPickupDetailsCurbsidePickupDetails`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `buyerArrivedAt` | `?string` | Optional | The [timestamp](https://developer.squareup.com/docs/build-basics/working-with-dates)<br>indicating when the buyer arrived and is waiting for pickup. The timestamp must be in RFC 3339 format<br>(for example, "2016-09-04T23:59:33.123Z"). | getBuyerArrivedAt(): ?string | setBuyerArrivedAt(?string buyerArrivedAt): void |
| `curbsideDetails` | `?string` | Optional | Specific details for curbside pickup, such as parking number and vehicle model.<br><br>**Constraints**: *Maximum Length*: `250` | getCurbsideDetails(): ?string | setCurbsideDetails(?string curbsideDetails): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\OrderFulfillmentPickupDetailsCurbsidePickupDetailsBuilder;

$orderFulfillmentPickupDetailsCurbsidePickupDetails = OrderFulfillmentPickupDetailsCurbsidePickupDetailsBuilder::init()
    ->buyerArrivedAt('buyer_arrived_at6')
    ->curbsideDetails('curbside_details0')
    ->build();
```

