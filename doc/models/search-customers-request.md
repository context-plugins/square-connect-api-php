
# Search Customers Request

Defines the fields that are included in the request body of a request to the
`SearchCustomers` endpoint.

## Structure

`SearchCustomersRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cursor` | `?string` | Optional | Include the pagination cursor in subsequent calls to this endpoint to retrieve<br>the next set of results associated with the original query.<br><br>For more information, see [Pagination](https://developer.squareup.com/docs/working-with-apis/pagination). | getCursor(): ?string | setCursor(?string cursor): void |
| `limit` | `?int` | Optional | The maximum number of results to return in a single page. This limit is advisory. The response might contain more or fewer results.<br>The limit is ignored if it is less than the minimum or greater than the maximum value. The default value is 100.<br><br>For more information, see [Pagination](https://developer.squareup.com/docs/working-with-apis/pagination).<br><br>**Constraints**: `>= 1`, `<= 100` | getLimit(): ?int | setLimit(?int limit): void |
| `query` | [`?CustomerQuery`](../../doc/models/customer-query.md) | Optional | Represents a query (including filtering criteria, sorting criteria, or both) used to search<br>for customer profiles. | getQuery(): ?CustomerQuery | setQuery(?CustomerQuery query): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\SearchCustomersRequestBuilder;
use SquareConnectAPILib\Models\Builders\CustomerQueryBuilder;
use SquareConnectAPILib\Models\Builders\CustomerFilterBuilder;
use SquareConnectAPILib\Models\Builders\TimeRangeBuilder;
use SquareConnectAPILib\Models\Builders\CustomerCreationSourceFilterBuilder;
use SquareConnectAPILib\Models\Builders\CustomerTextFilterBuilder;
use SquareConnectAPILib\Models\Builders\FilterValueBuilder;
use SquareConnectAPILib\Models\Builders\CustomerSortBuilder;

$searchCustomersRequest = SearchCustomersRequestBuilder::init()
    ->cursor('cursor6')
    ->limit(54)
    ->query(
        CustomerQueryBuilder::init()
            ->filter(
                CustomerFilterBuilder::init()
                    ->createdAt(
                        TimeRangeBuilder::init()
                            ->endAt('end_at8')
                            ->startAt('start_at4')
                            ->build()
                    )
                    ->creationSource(
                        CustomerCreationSourceFilterBuilder::init()
                            ->rule('rule6')
                            ->values(
                                [
                                    'values6',
                                    'values5',
                                    'values4'
                                ]
                            )
                            ->build()
                    )
                    ->emailAddress(
                        CustomerTextFilterBuilder::init()
                            ->exact('exact2')
                            ->fuzzy('fuzzy8')
                            ->build()
                    )
                    ->groupIds(
                        FilterValueBuilder::init()
                            ->all(
                                [
                                    'all5',
                                    'all4',
                                    'all3'
                                ]
                            )
                            ->any(
                                [
                                    'any2',
                                    'any3',
                                    'any4'
                                ]
                            )
                            ->none(
                                [
                                    'none7',
                                    'none8'
                                ]
                            )
                            ->build()
                    )
                    ->phoneNumber(
                        CustomerTextFilterBuilder::init()
                            ->exact('exact2')
                            ->fuzzy('fuzzy8')
                            ->build()
                    )
                    ->build()
            )
            ->sort(
                CustomerSortBuilder::init()
                    ->field('field2')
                    ->order('order8')
                    ->build()
            )
            ->build()
    )
    ->build();
```

