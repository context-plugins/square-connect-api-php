
# V1 Payment Modifier

V1PaymentModifier

## Structure

`V1PaymentModifier`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `appliedMoney` | [`?V1Money`](../../doc/models/v1-money.md) | Optional | - | getAppliedMoney(): ?V1Money | setAppliedMoney(?V1Money appliedMoney): void |
| `modifierOptionId` | `?string` | Optional | The ID of the applied modifier option, if available. Modifier options applied in older versions of Square Register might not have an ID. | getModifierOptionId(): ?string | setModifierOptionId(?string modifierOptionId): void |
| `name` | `?string` | Optional | The modifier option's name. | getName(): ?string | setName(?string name): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\V1PaymentModifierBuilder;
use SquareConnectAPILib\Models\Builders\V1MoneyBuilder;

$v1PaymentModifier = V1PaymentModifierBuilder::init()
    ->appliedMoney(
        V1MoneyBuilder::init()
            ->amount(196)
            ->currencyCode('currency_code4')
            ->build()
    )
    ->modifierOptionId('modifier_option_id8')
    ->name('name2')
    ->build();
```

