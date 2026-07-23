
# Gift Card Activity Block

Describes a gift card activity of the BLOCK type.

## Structure

`GiftCardActivityBlock`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `reason` | `array` | Required | - | getReason(): array | setReason(array reason): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\GiftCardActivityBlockBuilder;
use SquareConnectAPILib\ApiHelper;

$giftCardActivityBlock = GiftCardActivityBlockBuilder::init(
    ApiHelper::deserialize('{"key1":"val1","key2":"val2"}')
)->build();
```

