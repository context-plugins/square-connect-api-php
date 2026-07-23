
# Invoice Sort

Identifies the sort field and sort order.

## Structure

`InvoiceSort`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `field` | `string` | Required | The field to use for sorting. | getField(): string | setField(string field): void |
| `order` | `?string` | Optional | The order to use for sorting the results. | getOrder(): ?string | setOrder(?string order): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\InvoiceSortBuilder;

$invoiceSort = InvoiceSortBuilder::init(
    'field4'
)
    ->order('order4')
    ->build();
```

