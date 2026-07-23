
# Tender Cash Details

Represents the details of a tender with `type` `CASH`.

## Structure

`TenderCashDetails`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `buyerTenderedMoney` | [`?Money`](../../doc/models/money.md) | Optional | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getBuyerTenderedMoney(): ?Money | setBuyerTenderedMoney(?Money buyerTenderedMoney): void |
| `changeBackMoney` | [`?Money`](../../doc/models/money.md) | Optional | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getChangeBackMoney(): ?Money | setChangeBackMoney(?Money changeBackMoney): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\TenderCashDetailsBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;

$tenderCashDetails = TenderCashDetailsBuilder::init()
    ->buyerTenderedMoney(
        MoneyBuilder::init()
            ->amount(238)
            ->currency('currency4')
            ->build()
    )
    ->changeBackMoney(
        MoneyBuilder::init()
            ->amount(78)
            ->currency('currency6')
            ->build()
    )
    ->build();
```

