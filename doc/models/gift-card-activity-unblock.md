
# Gift Card Activity Unblock

Present only when `GiftCardActivityType` is UNBLOCK.

## Structure

`GiftCardActivityUnblock`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `reason` | `array` | Required | - | getReason(): array | setReason(array reason): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\GiftCardActivityUnblockBuilder;
use SquareConnectAPILib\ApiHelper;

$giftCardActivityUnblock = GiftCardActivityUnblockBuilder::init(
    ApiHelper::deserialize('{"key1":"val1","key2":"val2"}')
)->build();
```

