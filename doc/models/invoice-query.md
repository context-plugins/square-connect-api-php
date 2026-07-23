
# Invoice Query

Describes query criteria for searching invoices.

## Structure

`InvoiceQuery`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `filter` | [`InvoiceFilter`](../../doc/models/invoice-filter.md) | Required | Describes query filters to apply. | getFilter(): InvoiceFilter | setFilter(InvoiceFilter filter): void |
| `sort` | [`?InvoiceSort`](../../doc/models/invoice-sort.md) | Optional | Identifies the sort field and sort order. | getSort(): ?InvoiceSort | setSort(?InvoiceSort sort): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\InvoiceQueryBuilder;
use SquareConnectAPILib\Models\Builders\InvoiceFilterBuilder;
use SquareConnectAPILib\Models\Builders\InvoiceSortBuilder;

$invoiceQuery = InvoiceQueryBuilder::init(
    InvoiceFilterBuilder::init(
        [
            'location_ids4'
        ]
    )
        ->customerIds(
            [
                'customer_ids3',
                'customer_ids2'
            ]
        )
        ->build()
)
    ->sort(
        InvoiceSortBuilder::init(
            'field2'
        )
            ->order('order8')
            ->build()
    )
    ->build();
```

