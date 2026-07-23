
# Gift Card Activity Block Reason Enum

## Enumeration

`GiftCardActivityBlockReasonEnum`

## Fields

| Name | Description |
|  --- | --- |
| `CHARGEBACK_BLOCK` | The gift card is blocked because the buyer initiated a chargeback on the gift card purchase. |

## Example

```php
use SquareConnectAPILib\Models\GiftCardActivityBlockReasonEnum;

$giftCardActivityBlockReason = GiftCardActivityBlockReasonEnum::CHARGEBACK_BLOCK;
```

