
# Loyalty Reward Status Enum

The status of the loyalty reward.

## Enumeration

`LoyaltyRewardStatusEnum`

## Fields

| Name | Description |
|  --- | --- |
| `ISSUED` | The reward is issued. |
| `REDEEMED` | The reward is redeemed. |
| `DELETED` | The reward is deleted. |

## Example

```php
use SquareConnectAPILib\Models\LoyaltyRewardStatusEnum;

$loyaltyRewardStatus = LoyaltyRewardStatusEnum::DELETED;
```

