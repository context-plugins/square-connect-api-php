
# Invoice Custom Field Placement Enum

Indicates where to render a custom field on the Square-hosted invoice page and in emailed or PDF
copies of the invoice.

## Enumeration

`InvoiceCustomFieldPlacementEnum`

## Fields

| Name | Description |
|  --- | --- |
| `ABOVE_LINE_ITEMS` | Render the custom field above the invoice line items. |
| `BELOW_LINE_ITEMS` | Render the custom field below the invoice line items. |

## Example

```php
use SquareConnectAPILib\Models\InvoiceCustomFieldPlacementEnum;

$invoiceCustomFieldPlacement = InvoiceCustomFieldPlacementEnum::ABOVE_LINE_ITEMS;
```

