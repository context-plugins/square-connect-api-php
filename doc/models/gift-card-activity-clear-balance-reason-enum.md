
# Gift Card Activity Clear Balance Reason Enum

## Enumeration

`GiftCardActivityClearBalanceReasonEnum`

## Fields

| Name | Description |
|  --- | --- |
| `SUSPICIOUS_ACTIVITY` | The seller suspects suspicious activity. |
| `REUSE_GIFTCARD` | The seller cleared the balance to reuse the gift card. |
| `UNKNOWN_REASON` | The gift card balance was cleared for an unknown reason. |

## Example

```php
use SquareConnectAPILib\Models\GiftCardActivityClearBalanceReasonEnum;

$giftCardActivityClearBalanceReason = GiftCardActivityClearBalanceReasonEnum::UNKNOWN_REASON;
```

