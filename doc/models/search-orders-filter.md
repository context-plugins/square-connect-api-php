
# Search Orders Filter

Filtering criteria to use for a `SearchOrders` request. Multiple filters
are ANDed together.

## Structure

`SearchOrdersFilter`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `customerFilter` | [`?SearchOrdersCustomerFilter`](../../doc/models/search-orders-customer-filter.md) | Optional | A filter based on the order `customer_id` and any tender `customer_id`<br>associated with the order. It does not filter based on the<br>[FulfillmentRecipient](https://developer.squareup.com/reference/square_2021-08-18/objects/OrderFulfillmentRecipient) `customer_id`. | getCustomerFilter(): ?SearchOrdersCustomerFilter | setCustomerFilter(?SearchOrdersCustomerFilter customerFilter): void |
| `dateTimeFilter` | [`?SearchOrdersDateTimeFilter`](../../doc/models/search-orders-date-time-filter.md) | Optional | Filter for `Order` objects based on whether their `CREATED_AT`,<br>`CLOSED_AT`, or `UPDATED_AT` timestamps fall within a specified time range.<br>You can specify the time range and which timestamp to filter for. You can filter<br>for only one time range at a time.<br><br>For each time range, the start time and end time are inclusive. If the end time<br>is absent, it defaults to the time of the first request for the cursor.<br><br>__Important:__ If you use the `DateTimeFilter` in a `SearchOrders` query,<br>you must set the `sort_field` in [OrdersSort](https://developer.squareup.com/reference/square_2021-08-18/objects/SearchOrdersSort)<br>to the same field you filter for. For example, if you set the `CLOSED_AT` field<br>in `DateTimeFilter`, you must set the `sort_field` in `SearchOrdersSort` to<br>`CLOSED_AT`. Otherwise, `SearchOrders` throws an error.<br>[Learn more about filtering orders by time range.](https://developer.squareup.com/docs/orders-api/manage-orders#important-note-on-filtering-orders-by-time-range) | getDateTimeFilter(): ?SearchOrdersDateTimeFilter | setDateTimeFilter(?SearchOrdersDateTimeFilter dateTimeFilter): void |
| `fulfillmentFilter` | [`?SearchOrdersFulfillmentFilter`](../../doc/models/search-orders-fulfillment-filter.md) | Optional | Filter based on [order fulfillment](https://developer.squareup.com/reference/square_2021-08-18/objects/OrderFulfillment) information. | getFulfillmentFilter(): ?SearchOrdersFulfillmentFilter | setFulfillmentFilter(?SearchOrdersFulfillmentFilter fulfillmentFilter): void |
| `sourceFilter` | [`?SearchOrdersSourceFilter`](../../doc/models/search-orders-source-filter.md) | Optional | A filter based on order `source` information. | getSourceFilter(): ?SearchOrdersSourceFilter | setSourceFilter(?SearchOrdersSourceFilter sourceFilter): void |
| `stateFilter` | [`?SearchOrdersStateFilter`](../../doc/models/search-orders-state-filter.md) | Optional | Filter by the current order `state`. | getStateFilter(): ?SearchOrdersStateFilter | setStateFilter(?SearchOrdersStateFilter stateFilter): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\SearchOrdersFilterBuilder;
use SquareConnectAPILib\Models\Builders\SearchOrdersCustomerFilterBuilder;
use SquareConnectAPILib\Models\Builders\SearchOrdersDateTimeFilterBuilder;
use SquareConnectAPILib\Models\Builders\TimeRangeBuilder;
use SquareConnectAPILib\Models\Builders\SearchOrdersFulfillmentFilterBuilder;
use SquareConnectAPILib\Models\Builders\SearchOrdersSourceFilterBuilder;
use SquareConnectAPILib\Models\Builders\SearchOrdersStateFilterBuilder;

$searchOrdersFilter = SearchOrdersFilterBuilder::init()
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
    )->build();
```

