
# Gift Card Activity Adjust Increment

Describes a gift card activity of the ADJUST_INCREMENT type.

## Structure

`GiftCardActivityAdjustIncrement`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amountMoney` | [`Money`](../../doc/models/money.md) | Required | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getAmountMoney(): Money | setAmountMoney(Money amountMoney): void |
| `reason` | `array` | Required | - | getReason(): array | setReason(array reason): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\GiftCardActivityAdjustIncrementBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;
use SquareConnectAPILib\ApiHelper;

$giftCardActivityAdjustIncrement = GiftCardActivityAdjustIncrementBuilder::init(
    MoneyBuilder::init()
        ->amount(186)
        ->currency('currency8')
        ->build(),
    ApiHelper::deserialize('{"key1":"val1","key2":"val2"}')
)->build();
```

