
# Order Money Amounts

A collection of various money amounts.

## Structure

`OrderMoneyAmounts`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `discountMoney` | [`?Money`](../../doc/models/money.md) | Optional | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getDiscountMoney(): ?Money | setDiscountMoney(?Money discountMoney): void |
| `serviceChargeMoney` | [`?Money`](../../doc/models/money.md) | Optional | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getServiceChargeMoney(): ?Money | setServiceChargeMoney(?Money serviceChargeMoney): void |
| `taxMoney` | [`?Money`](../../doc/models/money.md) | Optional | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getTaxMoney(): ?Money | setTaxMoney(?Money taxMoney): void |
| `tipMoney` | [`?Money`](../../doc/models/money.md) | Optional | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getTipMoney(): ?Money | setTipMoney(?Money tipMoney): void |
| `totalMoney` | [`?Money`](../../doc/models/money.md) | Optional | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getTotalMoney(): ?Money | setTotalMoney(?Money totalMoney): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\OrderMoneyAmountsBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;

$orderMoneyAmounts = OrderMoneyAmountsBuilder::init()
    ->discountMoney(
        MoneyBuilder::init()
            ->amount(92)
            ->currency('currency4')
            ->build()
    )
    ->serviceChargeMoney(
        MoneyBuilder::init()
            ->amount(160)
            ->currency('currency6')
            ->build()
    )
    ->taxMoney(
        MoneyBuilder::init()
            ->amount(58)
            ->currency('currency0')
            ->build()
    )
    ->tipMoney(
        MoneyBuilder::init()
            ->amount(190)
            ->currency('currency4')
            ->build()
    )
    ->totalMoney(
        MoneyBuilder::init()
            ->amount(250)
            ->currency('currency8')
            ->build()
    )
    ->build();
```

