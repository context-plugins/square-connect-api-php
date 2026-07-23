
# Search Subscriptions Request

Defines parameters in a
[SearchSubscriptions](https://developer.squareup.com/reference/square_2021-08-18/subscriptions-api/search-subscriptions) endpoint
request.

## Structure

`SearchSubscriptionsRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cursor` | `?string` | Optional | A pagination cursor returned by a previous call to this endpoint.<br>Provide this to retrieve the next set of results for the original query.<br><br>For more information, see [Pagination](https://developer.squareup.com/docs/working-with-apis/pagination). | getCursor(): ?string | setCursor(?string cursor): void |
| `limit` | `?int` | Optional | The upper limit on the number of subscriptions to return<br>in the response.<br><br>Default: `200`<br><br>**Constraints**: `>= 1` | getLimit(): ?int | setLimit(?int limit): void |
| `query` | [`?SearchSubscriptionsQuery`](../../doc/models/search-subscriptions-query.md) | Optional | Represents a query (including filtering criteria) used to search for subscriptions. | getQuery(): ?SearchSubscriptionsQuery | setQuery(?SearchSubscriptionsQuery query): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\SearchSubscriptionsRequestBuilder;
use SquareConnectAPILib\Models\Builders\SearchSubscriptionsQueryBuilder;
use SquareConnectAPILib\Models\Builders\SearchSubscriptionsFilterBuilder;

$searchSubscriptionsRequest = SearchSubscriptionsRequestBuilder::init()
    ->cursor('cursor4')
    ->limit(138)
    ->query(
        SearchSubscriptionsQueryBuilder::init()
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
            ->build()
    )
    ->build();
```

