
# Tax Calculation Phase Enum

When to calculate the taxes due on a cart.

## Enumeration

`TaxCalculationPhaseEnum`

## Fields

| Name | Description |
|  --- | --- |
| `TAX_SUBTOTAL_PHASE` | The fee is calculated based on the payment's subtotal. |
| `TAX_TOTAL_PHASE` | The fee is calculated based on the payment's total. |

## Example

```php
use SquareConnectAPILib\Models\TaxCalculationPhaseEnum;

$taxCalculationPhase = TaxCalculationPhaseEnum::TAX_SUBTOTAL_PHASE;
```

