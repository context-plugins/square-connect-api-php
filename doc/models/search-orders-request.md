
# Search Orders Request

The request does not have any required fields. When given no query criteria,
`SearchOrders` returns all results for all of the seller's locations. When retrieving additional
pages using a `cursor`, the `query` must be equal to the `query` used to retrieve the first page of
results.

## Structure

`SearchOrdersRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cursor` | `?string` | Optional | A pagination cursor returned by a previous call to this endpoint.<br>Provide this cursor to retrieve the next set of results for your original query.<br>For more information, see [Pagination](https://developer.squareup.com/docs/basics/api101/pagination). | getCursor(): ?string | setCursor(?string cursor): void |
| `limit` | `?int` | Optional | The maximum number of results to be returned in a single page. It is<br>possible to receive fewer results than the specified limit on a given page.<br><br>Default: `500`<br><br>**Constraints**: `>= 1` | getLimit(): ?int | setLimit(?int limit): void |
| `locationIds` | `?(string[])` | Optional | The location IDs for the orders to query. All locations must belong to<br>the same merchant.<br><br>Min: 1 location ID.<br><br>Max: 10 location IDs. | getLocationIds(): ?array | setLocationIds(?array locationIds): void |
| `query` | [`?SearchOrdersQuery`](../../doc/models/search-orders-query.md) | Optional | Contains query criteria for the search. | getQuery(): ?SearchOrdersQuery | setQuery(?SearchOrdersQuery query): void |
| `returnEntries` | `?bool` | Optional | A Boolean that controls the format of the search results. If `true`,<br>`SearchOrders` returns [OrderEntry](https://developer.squareup.com/reference/square_2021-08-18/objects/OrderEntry) objects. If `false`, `SearchOrders`<br>returns complete order objects.<br><br>Default: `false`. | getReturnEntries(): ?bool | setReturnEntries(?bool returnEntries): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\SearchOrdersRequestBuilder;
use SquareConnectAPILib\Models\Builders\SearchOrdersQueryBuilder;
use SquareConnectAPILib\Models\Builders\SearchOrdersFilterBuilder;
use SquareConnectAPILib\Models\Builders\SearchOrdersCustomerFilterBuilder;
use SquareConnectAPILib\Models\Builders\SearchOrdersDateTimeFilterBuilder;
use SquareConnectAPILib\Models\Builders\TimeRangeBuilder;
use SquareConnectAPILib\Models\Builders\SearchOrdersFulfillmentFilterBuilder;
use SquareConnectAPILib\Models\Builders\SearchOrdersSourceFilterBuilder;
use SquareConnectAPILib\Models\Builders\SearchOrdersStateFilterBuilder;
use SquareConnectAPILib\Models\Builders\SearchOrdersSortBuilder;

$searchOrdersRequest = SearchOrdersRequestBuilder::init()
    ->cursor('cursor4')
    ->limit(134)
    ->locationIds(
        [
            'location_ids2'
        ]
    )
    ->query(
        SearchOrdersQueryBuilder::init()
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
            ->build()
    )
    ->returnEntries(false)
    ->build();
```

