
# Gift Card Activity Adjust Increment Reason Enum

## Enumeration

`GiftCardActivityAdjustIncrementReasonEnum`

## Fields

| Name | Description |
|  --- | --- |
| `COMPLIMENTARY` | Seller gifted a complimentary gift card balance increase. |
| `SUPPORT_ISSUE` | The seller increased the gift card balance<br>to accommodate support issues. |
| `TRANSACTION_VOIDED` | The transaction is voided. |

## Example

```php
use SquareConnectAPILib\Models\GiftCardActivityAdjustIncrementReasonEnum;

$giftCardActivityAdjustIncrementReason = GiftCardActivityAdjustIncrementReasonEnum::TRANSACTION_VOIDED;
```

