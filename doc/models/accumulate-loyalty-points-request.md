
# Accumulate Loyalty Points Request

A request to accumulate points for a purchase.

## Structure

`AccumulateLoyaltyPointsRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accumulatePoints` | [`LoyaltyEventAccumulatePoints`](../../doc/models/loyalty-event-accumulate-points.md) | Required | Provides metadata when the event `type` is `ACCUMULATE_POINTS`. | getAccumulatePoints(): LoyaltyEventAccumulatePoints | setAccumulatePoints(LoyaltyEventAccumulatePoints accumulatePoints): void |
| `idempotencyKey` | `string` | Required | A unique string that identifies the `AccumulateLoyaltyPoints` request.<br>Keys can be any valid string but must be unique for every request.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `128` | getIdempotencyKey(): string | setIdempotencyKey(string idempotencyKey): void |
| `locationId` | `string` | Required | The [location](https://developer.squareup.com/reference/square_2021-08-18/objects/Location) where the purchase was made. | getLocationId(): string | setLocationId(string locationId): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\AccumulateLoyaltyPointsRequestBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyEventAccumulatePointsBuilder;

$accumulateLoyaltyPointsRequest = AccumulateLoyaltyPointsRequestBuilder::init(
    LoyaltyEventAccumulatePointsBuilder::init()
        ->loyaltyProgramId('loyalty_program_id8')
        ->orderId('order_id8')
        ->points(118)
        ->build(),
    'idempotency_key6',
    'location_id4'
)->build();
```

