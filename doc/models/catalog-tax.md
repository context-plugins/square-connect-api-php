
# Catalog Tax

A tax applicable to an item.

## Structure

`CatalogTax`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `appliesToCustomAmounts` | `?bool` | Optional | If `true`, the fee applies to custom amounts entered into the Square Point of Sale<br>app that are not associated with a particular `CatalogItem`. | getAppliesToCustomAmounts(): ?bool | setAppliesToCustomAmounts(?bool appliesToCustomAmounts): void |
| `calculationPhase` | `?string` | Optional | Whether the tax is calculated based on a payment's subtotal or total. | getCalculationPhase(): ?string | setCalculationPhase(?string calculationPhase): void |
| `enabled` | `?bool` | Optional | A Boolean flag to indicate whether the tax is displayed as enabled (`true`) in the Square Point of Sale app or not (`false`). | getEnabled(): ?bool | setEnabled(?bool enabled): void |
| `inclusionType` | `?string` | Optional | Whether the tax is `ADDITIVE` or `INCLUSIVE`. | getInclusionType(): ?string | setInclusionType(?string inclusionType): void |
| `name` | `?string` | Optional | The tax's name. This is a searchable attribute for use in applicable query filters, and its value length is of Unicode code points.<br><br>**Constraints**: *Maximum Length*: `255` | getName(): ?string | setName(?string name): void |
| `percentage` | `?string` | Optional | The percentage of the tax in decimal form, using a `'.'` as the decimal separator and without a `'%'` sign.<br>A value of `7.5` corresponds to 7.5%. | getPercentage(): ?string | setPercentage(?string percentage): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CatalogTaxBuilder;

$catalogTax = CatalogTaxBuilder::init()
    ->appliesToCustomAmounts(false)
    ->calculationPhase('calculation_phase4')
    ->enabled(false)
    ->inclusionType('inclusion_type0')
    ->name('name4')
    ->build();
```

