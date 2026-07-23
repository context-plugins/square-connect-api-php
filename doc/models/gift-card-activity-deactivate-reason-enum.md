
# Gift Card Activity Deactivate Reason Enum

## Enumeration

`GiftCardActivityDeactivateReasonEnum`

## Fields

| Name | Description |
|  --- | --- |
| `SUSPICIOUS_ACTIVITY` | The seller suspects suspicious activity. |
| `UNKNOWN_REASON` | The gift card deactivated for an unknown reason. |
| `CHARGEBACK_DEACTIVATE` | A chargeback on the gift card purchase (or the gift card load) was ruled in favor of the buyer. |

## Example

```php
use SquareConnectAPILib\Models\GiftCardActivityDeactivateReasonEnum;

$giftCardActivityDeactivateReason = GiftCardActivityDeactivateReasonEnum::CHARGEBACK_DEACTIVATE;
```

