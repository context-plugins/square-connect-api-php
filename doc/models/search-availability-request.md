
# Search Availability Request

## Structure

`SearchAvailabilityRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `query` | [`SearchAvailabilityQuery`](../../doc/models/search-availability-query.md) | Required | Query conditions to search for availabilities of bookings. | getQuery(): SearchAvailabilityQuery | setQuery(SearchAvailabilityQuery query): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\SearchAvailabilityRequestBuilder;
use SquareConnectAPILib\Models\Builders\SearchAvailabilityQueryBuilder;
use SquareConnectAPILib\Models\Builders\SearchAvailabilityFilterBuilder;
use SquareConnectAPILib\Models\Builders\TimeRangeBuilder;
use SquareConnectAPILib\Models\Builders\SegmentFilterBuilder;
use SquareConnectAPILib\Models\Builders\FilterValueBuilder;

$searchAvailabilityRequest = SearchAvailabilityRequestBuilder::init(
    SearchAvailabilityQueryBuilder::init(
        SearchAvailabilityFilterBuilder::init(
            TimeRangeBuilder::init()
                ->endAt('2020-11-27T13:00:00Z')
                ->startAt('2020-11-26T13:00:00Z')
                ->build()
        )
            ->bookingId('booking_id8')
            ->locationId('LEQHH0YY8B42M')
            ->segmentFilters(
                [
                    SegmentFilterBuilder::init(
                        'RU3PBTZTK7DXZDQFCJHOK2MC'
                    )
                        ->teamMemberIdFilter(
                            FilterValueBuilder::init()
                                ->all(
                                    [
                                        'all5',
                                        'all6',
                                        'all7'
                                    ]
                                )
                                ->any(
                                    [
                                        'TMXUrsBWWcHTt79t',
                                        'TMaJcbiRqPIGZuS9'
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
                        ->build()
                ]
            )
            ->build()
    )->build()
)->build();
```

