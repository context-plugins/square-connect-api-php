
# Gift Card Activity Adjust Decrement Reason Enum

## Enumeration

`GiftCardActivityAdjustDecrementReasonEnum`

## Fields

| Name | Description |
|  --- | --- |
| `SUSPICIOUS_ACTIVITY` | The seller determined suspicious activity by the buyer. |
| `BALANCE_ACCIDENTALLY_INCREASED` | The seller previously increased the gift card balance by accident. |
| `SUPPORT_ISSUE` | The seller decreased the gift card balance to<br>accommodate support issues. |

## Example

```php
use SquareConnectAPILib\Models\GiftCardActivityAdjustDecrementReasonEnum;

$giftCardActivityAdjustDecrementReason = GiftCardActivityAdjustDecrementReasonEnum::SUSPICIOUS_ACTIVITY;
```

