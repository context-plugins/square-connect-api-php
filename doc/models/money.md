
# Money

Represents an amount of money. `Money` fields can be signed or unsigned.
Fields that do not explicitly define whether they are signed or unsigned are
considered unsigned and can only hold positive amounts. For signed fields, the
sign of the value indicates the purpose of the money transfer. See
[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)
for more information.

## Structure

`Money`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amount` | `?int` | Optional | The amount of money, in the smallest denomination of the currency<br>indicated by `currency`. For example, when `currency` is `USD`, `amount` is<br>in cents. Monetary amounts can be positive or negative. See the specific<br>field description to determine the meaning of the sign in a particular case. | getAmount(): ?int | setAmount(?int amount): void |
| `currency` | `?string` | Optional | The type of currency, in __ISO 4217 format__. For example, the currency<br>code for US dollars is `USD`.<br><br>See [Currency](https://developer.squareup.com/reference/square_2021-08-18/enums/Currency) for possible values. | getCurrency(): ?string | setCurrency(?string currency): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\MoneyBuilder;

$money = MoneyBuilder::init()
    ->amount(0)
    ->currency('currency8')
    ->build();
```

