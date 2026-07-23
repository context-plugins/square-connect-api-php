
# Search Invoices Request

Describes a `SearchInvoices` request.

## Structure

`SearchInvoicesRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cursor` | `?string` | Optional | A pagination cursor returned by a previous call to this endpoint.<br>Provide this cursor to retrieve the next set of results for your original query.<br><br>For more information, see [Pagination](https://developer.squareup.com/docs/working-with-apis/pagination). | getCursor(): ?string | setCursor(?string cursor): void |
| `limit` | `?int` | Optional | The maximum number of invoices to return (200 is the maximum `limit`).<br>If not provided, the server uses a default limit of 100 invoices. | getLimit(): ?int | setLimit(?int limit): void |
| `query` | [`InvoiceQuery`](../../doc/models/invoice-query.md) | Required | Describes query criteria for searching invoices. | getQuery(): InvoiceQuery | setQuery(InvoiceQuery query): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\SearchInvoicesRequestBuilder;
use SquareConnectAPILib\Models\Builders\InvoiceQueryBuilder;
use SquareConnectAPILib\Models\Builders\InvoiceFilterBuilder;
use SquareConnectAPILib\Models\Builders\InvoiceSortBuilder;

$searchInvoicesRequest = SearchInvoicesRequestBuilder::init(
    InvoiceQueryBuilder::init(
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
        ->build()
)
    ->cursor('cursor6')
    ->limit(244)
    ->build();
```

