
# Search Subscriptions Query

Represents a query (including filtering criteria) used to search for subscriptions.

## Structure

`SearchSubscriptionsQuery`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `filter` | [`?SearchSubscriptionsFilter`](../../doc/models/search-subscriptions-filter.md) | Optional | Represents a set of SearchSubscriptionsQuery filters used to limit the set of Subscriptions returned by SearchSubscriptions. | getFilter(): ?SearchSubscriptionsFilter | setFilter(?SearchSubscriptionsFilter filter): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\SearchSubscriptionsQueryBuilder;
use SquareConnectAPILib\Models\Builders\SearchSubscriptionsFilterBuilder;

$searchSubscriptionsQuery = SearchSubscriptionsQueryBuilder::init()
    ->filter(
        SearchSubscriptionsFilterBuilder::init()
            ->customerIds(
                [
                    'customer_ids3',
                    'customer_ids2'
                ]
            )
            ->locationIds(
                [
                    'location_ids4'
                ]
            )
            ->build()
    )
    ->build();
```

