
# V1 Money

## Structure

`V1Money`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amount` | `?int` | Optional | Amount in the lowest denominated value of this Currency. E.g. in USD<br>these are cents, in JPY they are Yen (which do not have a 'cent' concept). | getAmount(): ?int | setAmount(?int amount): void |
| `currencyCode` | `?string` | Optional | - | getCurrencyCode(): ?string | setCurrencyCode(?string currencyCode): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\V1MoneyBuilder;

$v1Money = V1MoneyBuilder::init()
    ->amount(206)
    ->currencyCode('currency_code2')
    ->build();
```

