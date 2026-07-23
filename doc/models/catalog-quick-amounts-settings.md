
# Catalog Quick Amounts Settings

A parent Catalog Object model represents a set of Quick Amounts and the settings control the amounts.

## Structure

`CatalogQuickAmountsSettings`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amounts` | [`?(CatalogQuickAmount[])`](../../doc/models/catalog-quick-amount.md) | Optional | Represents a set of Quick Amounts at this location. | getAmounts(): ?array | setAmounts(?array amounts): void |
| `eligibleForAutoAmounts` | `?bool` | Optional | Represents location's eligibility for auto amounts<br>The boolean should be consistent with whether there are AUTO amounts in the `amounts`. | getEligibleForAutoAmounts(): ?bool | setEligibleForAutoAmounts(?bool eligibleForAutoAmounts): void |
| `option` | `string` | Required | Represents the option seller currently uses on Quick Amounts. | getOption(): string | setOption(string option): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CatalogQuickAmountsSettingsBuilder;
use SquareConnectAPILib\Models\Builders\CatalogQuickAmountBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;

$catalogQuickAmountsSettings = CatalogQuickAmountsSettingsBuilder::init(
    'option2'
)
    ->amounts(
        [
            CatalogQuickAmountBuilder::init(
                MoneyBuilder::init()
                    ->amount(0)
                    ->currency('currency2')
                    ->build(),
                'type4'
            )
                ->ordinal(48)
                ->score(116)
                ->build(),
            CatalogQuickAmountBuilder::init(
                MoneyBuilder::init()
                    ->amount(0)
                    ->currency('currency2')
                    ->build(),
                'type4'
            )
                ->ordinal(48)
                ->score(116)
                ->build()
        ]
    )
    ->eligibleForAutoAmounts(false)
    ->build();
```

