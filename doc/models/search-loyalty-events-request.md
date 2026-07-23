
# Search Loyalty Events Request

A request to search for loyalty events.

## Structure

`SearchLoyaltyEventsRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cursor` | `?string` | Optional | A pagination cursor returned by a previous call to this endpoint.<br>Provide this to retrieve the next set of results for your original query.<br>For more information, see [Pagination](https://developer.squareup.com/docs/basics/api101/pagination). | getCursor(): ?string | setCursor(?string cursor): void |
| `limit` | `?int` | Optional | The maximum number of results to include in the response.<br>The last page might contain fewer events.<br>The default is 30 events.<br><br>**Constraints**: `>= 1`, `<= 30` | getLimit(): ?int | setLimit(?int limit): void |
| `query` | [`?LoyaltyEventQuery`](../../doc/models/loyalty-event-query.md) | Optional | Represents a query used to search for loyalty events. | getQuery(): ?LoyaltyEventQuery | setQuery(?LoyaltyEventQuery query): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\SearchLoyaltyEventsRequestBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyEventQueryBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyEventFilterBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyEventDateTimeFilterBuilder;
use SquareConnectAPILib\Models\Builders\TimeRangeBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyEventLocationFilterBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyEventLoyaltyAccountFilterBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyEventOrderFilterBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyEventTypeFilterBuilder;

$searchLoyaltyEventsRequest = SearchLoyaltyEventsRequestBuilder::init()
    ->cursor('cursor6')
    ->limit(30)
    ->query(
        LoyaltyEventQueryBuilder::init()
            ->filter(
                LoyaltyEventFilterBuilder::init()
                    ->dateTimeFilter(
                        LoyaltyEventDateTimeFilterBuilder::init(
                            TimeRangeBuilder::init()
                                ->endAt('end_at8')
                                ->startAt('start_at4')
                                ->build()
                        )->build()
                    )
                    ->locationFilter(
                        LoyaltyEventLocationFilterBuilder::init(
                            [
                                'location_ids0',
                                'location_ids1',
                                'location_ids2'
                            ]
                        )->build()
                    )
                    ->loyaltyAccountFilter(
                        LoyaltyEventLoyaltyAccountFilterBuilder::init(
                            'loyalty_account_id8'
                        )->build()
                    )
                    ->orderFilter(
                        LoyaltyEventOrderFilterBuilder::init(
                            'order_id2'
                        )->build()
                    )
                    ->typeFilter(
                        LoyaltyEventTypeFilterBuilder::init(
                            [
                                'types5',
                                'types6',
                                'types7'
                            ]
                        )->build()
                    )->build()
            )->build()
    )->build();
```

