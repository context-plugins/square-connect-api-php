
# Order Line Item Tax Scope Enum

Indicates whether this is a line-item or order-level tax.

## Enumeration

`OrderLineItemTaxScopeEnum`

## Fields

| Name | Description |
|  --- | --- |
| `OTHER_TAX_SCOPE` | Used for reporting only.<br>The original transaction tax scope is currently not supported by the API. |
| `LINE_ITEM` | The tax should be applied only to line items specified by<br>the `OrderLineItemAppliedTax` reference records. |
| `ORDER` | The tax should be applied to the entire order. |

## Example

```php
use SquareConnectAPILib\Models\OrderLineItemTaxScopeEnum;

$orderLineItemTaxScope = OrderLineItemTaxScopeEnum::LINE_ITEM;
```

