
# Search Orders Query

Contains query criteria for the search.

## Structure

`SearchOrdersQuery`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `filter` | [`?SearchOrdersFilter`](../../doc/models/search-orders-filter.md) | Optional | Filtering criteria to use for a `SearchOrders` request. Multiple filters<br>are ANDed together. | getFilter(): ?SearchOrdersFilter | setFilter(?SearchOrdersFilter filter): void |
| `sort` | [`?SearchOrdersSort`](../../doc/models/search-orders-sort.md) | Optional | Sorting criteria for a `SearchOrders` request. Results can only be sorted<br>by a timestamp field. | getSort(): ?SearchOrdersSort | setSort(?SearchOrdersSort sort): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\SearchOrdersQueryBuilder;
use SquareConnectAPILib\Models\Builders\SearchOrdersFilterBuilder;
use SquareConnectAPILib\Models\Builders\SearchOrdersCustomerFilterBuilder;
use SquareConnectAPILib\Models\Builders\SearchOrdersDateTimeFilterBuilder;
use SquareConnectAPILib\Models\Builders\TimeRangeBuilder;
use SquareConnectAPILib\Models\Builders\SearchOrdersFulfillmentFilterBuilder;
use SquareConnectAPILib\Models\Builders\SearchOrdersSourceFilterBuilder;
use SquareConnectAPILib\Models\Builders\SearchOrdersStateFilterBuilder;
use SquareConnectAPILib\Models\Builders\SearchOrdersSortBuilder;

$searchOrdersQuery = SearchOrdersQueryBuilder::init()
    ->filter(
        SearchOrdersFilterBuilder::init()
            ->customerFilter(
                SearchOrdersCustomerFilterBuilder::init()
                    ->customerIds(
                        [
                            'customer_ids3',
                            'customer_ids4'
                        ]
                    )
                    ->build()
            )
            ->dateTimeFilter(
                SearchOrdersDateTimeFilterBuilder::init()
                    ->closedAt(
                        TimeRangeBuilder::init()
                            ->endAt('end_at8')
                            ->startAt('start_at4')
                            ->build()
                    )
                    ->createdAt(
                        TimeRangeBuilder::init()
                            ->endAt('end_at8')
                            ->startAt('start_at4')
                            ->build()
                    )
                    ->updatedAt(
                        TimeRangeBuilder::init()
                            ->endAt('end_at6')
                            ->startAt('start_at6')
                            ->build()
                    )
                    ->build()
            )
            ->fulfillmentFilter(
                SearchOrdersFulfillmentFilterBuilder::init()
                    ->fulfillmentStates(
                        [
                            'fulfillment_states6',
                            'fulfillment_states7'
                        ]
                    )
                    ->fulfillmentTypes(
                        [
                            'fulfillment_types3'
                        ]
                    )
                    ->build()
            )
            ->sourceFilter(
                SearchOrdersSourceFilterBuilder::init()
                    ->sourceNames(
                        [
                            'source_names6'
                        ]
                    )
                    ->build()
            )
            ->stateFilter(
                SearchOrdersStateFilterBuilder::init(
                    [
                        'states8',
                        'states9'
                    ]
                )->build()
            )->build()
    )
    ->sort(
        SearchOrdersSortBuilder::init(
            'sort_field0'
        )
            ->sortOrder('sort_order8')
            ->build()
    )
    ->build();
```

