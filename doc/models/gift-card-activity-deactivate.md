
# Gift Card Activity Deactivate

Describes a gift card activity of the DEACTIVATE type.

## Structure

`GiftCardActivityDeactivate`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `reason` | `array` | Required | - | getReason(): array | setReason(array reason): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\GiftCardActivityDeactivateBuilder;
use SquareConnectAPILib\ApiHelper;

$giftCardActivityDeactivate = GiftCardActivityDeactivateBuilder::init(
    ApiHelper::deserialize('{"key1":"val1","key2":"val2"}')
)->build();
```

