
# Customer Query

Represents a query (including filtering criteria, sorting criteria, or both) used to search
for customer profiles.

## Structure

`CustomerQuery`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `filter` | [`?CustomerFilter`](../../doc/models/customer-filter.md) | Optional | Represents a set of `CustomerQuery` filters used to limit the set of<br>customers returned by the [SearchCustomers](https://developer.squareup.com/reference/square_2021-08-18/customers-api/search-customers) endpoint. | getFilter(): ?CustomerFilter | setFilter(?CustomerFilter filter): void |
| `sort` | [`?CustomerSort`](../../doc/models/customer-sort.md) | Optional | Specifies how searched customers profiles are sorted, including the sort key and sort order. | getSort(): ?CustomerSort | setSort(?CustomerSort sort): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CustomerQueryBuilder;
use SquareConnectAPILib\Models\Builders\CustomerFilterBuilder;
use SquareConnectAPILib\Models\Builders\TimeRangeBuilder;
use SquareConnectAPILib\Models\Builders\CustomerCreationSourceFilterBuilder;
use SquareConnectAPILib\Models\Builders\CustomerTextFilterBuilder;
use SquareConnectAPILib\Models\Builders\FilterValueBuilder;
use SquareConnectAPILib\Models\Builders\CustomerSortBuilder;

$customerQuery = CustomerQueryBuilder::init()
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
    ->build();
```

