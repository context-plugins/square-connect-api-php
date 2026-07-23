
# Adjust Loyalty Points Request

A request to adjust (add or subtract) points manually.

## Structure

`AdjustLoyaltyPointsRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `adjustPoints` | [`LoyaltyEventAdjustPoints`](../../doc/models/loyalty-event-adjust-points.md) | Required | Provides metadata when the event `type` is `ADJUST_POINTS`. | getAdjustPoints(): LoyaltyEventAdjustPoints | setAdjustPoints(LoyaltyEventAdjustPoints adjustPoints): void |
| `idempotencyKey` | `string` | Required | A unique string that identifies this `AdjustLoyaltyPoints` request.<br>Keys can be any valid string, but must be unique for every request.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `128` | getIdempotencyKey(): string | setIdempotencyKey(string idempotencyKey): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\AdjustLoyaltyPointsRequestBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyEventAdjustPointsBuilder;

$adjustLoyaltyPointsRequest = AdjustLoyaltyPointsRequestBuilder::init(
    LoyaltyEventAdjustPointsBuilder::init(
        96
    )
        ->loyaltyProgramId('loyalty_program_id2')
        ->reason('reason2')
        ->build(),
    'idempotency_key0'
)->build();
```

