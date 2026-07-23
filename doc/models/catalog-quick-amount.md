
# Catalog Quick Amount

Represents a Quick Amount in the Catalog.

## Structure

`CatalogQuickAmount`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amount` | [`Money`](../../doc/models/money.md) | Required | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getAmount(): Money | setAmount(Money amount): void |
| `ordinal` | `?int` | Optional | The order in which this Quick Amount should be displayed. | getOrdinal(): ?int | setOrdinal(?int ordinal): void |
| `score` | `?int` | Optional | Describes the ranking of the Quick Amount provided by machine learning model, in the range [0, 100].<br>MANUAL type amount will always have score = 100. | getScore(): ?int | setScore(?int score): void |
| `type` | `string` | Required | Represents the type of the Quick Amount. | getType(): string | setType(string type): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CatalogQuickAmountBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;

$catalogQuickAmount = CatalogQuickAmountBuilder::init(
    MoneyBuilder::init()
        ->amount(0)
        ->currency('currency2')
        ->build(),
    'type0'
)
    ->ordinal(50)
    ->score(118)
    ->build();
```

