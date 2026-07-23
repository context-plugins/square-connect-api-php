
# Redeem Loyalty Reward Request

A request to redeem a loyalty reward.

## Structure

`RedeemLoyaltyRewardRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `idempotencyKey` | `string` | Required | A unique string that identifies this `RedeemLoyaltyReward` request.<br>Keys can be any valid string, but must be unique for every request.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `128` | getIdempotencyKey(): string | setIdempotencyKey(string idempotencyKey): void |
| `locationId` | `string` | Required | The ID of the [location](https://developer.squareup.com/reference/square_2021-08-18/objects/Location) where the reward is redeemed.<br><br>**Constraints**: *Minimum Length*: `1` | getLocationId(): string | setLocationId(string locationId): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\RedeemLoyaltyRewardRequestBuilder;

$redeemLoyaltyRewardRequest = RedeemLoyaltyRewardRequestBuilder::init(
    'idempotency_key4',
    'location_id2'
)->build();
```

