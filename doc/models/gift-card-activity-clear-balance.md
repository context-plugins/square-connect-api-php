
# Gift Card Activity Clear Balance

Describes a gift card activity of the CLEAR_BALANCE type.

## Structure

`GiftCardActivityClearBalance`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `reason` | `array` | Required | - | getReason(): array | setReason(array reason): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\GiftCardActivityClearBalanceBuilder;
use SquareConnectAPILib\ApiHelper;

$giftCardActivityClearBalance = GiftCardActivityClearBalanceBuilder::init(
    ApiHelper::deserialize('{"key1":"val1","key2":"val2"}')
)->build();
```

