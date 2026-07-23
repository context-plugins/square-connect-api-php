
# Invoice Sort Field Enum

The field to use for sorting.

## Enumeration

`InvoiceSortFieldEnum`

## Fields

| Name | Description |
|  --- | --- |
| `INVOICE_SORT_DATE` | The field works as follows:<br><br>- If the invoice is a draft, it uses the invoice `created_at` date.<br>- If the invoice is scheduled for publication, it uses the `scheduled_at` date.<br>- If the invoice is published, it uses the invoice publication date. |

## Example

```php
use SquareConnectAPILib\Models\InvoiceSortFieldEnum;

$invoiceSortField = InvoiceSortFieldEnum::INVOICE_SORT_DATE;
```

