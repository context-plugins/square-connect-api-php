
# Search Availability Query

Query conditions to search for availabilities of bookings.

## Structure

`SearchAvailabilityQuery`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `filter` | [`SearchAvailabilityFilter`](../../doc/models/search-availability-filter.md) | Required | A query filter to search for availabilities by. | getFilter(): SearchAvailabilityFilter | setFilter(SearchAvailabilityFilter filter): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\SearchAvailabilityQueryBuilder;
use SquareConnectAPILib\Models\Builders\SearchAvailabilityFilterBuilder;
use SquareConnectAPILib\Models\Builders\TimeRangeBuilder;
use SquareConnectAPILib\Models\Builders\SegmentFilterBuilder;
use SquareConnectAPILib\Models\Builders\FilterValueBuilder;

$searchAvailabilityQuery = SearchAvailabilityQueryBuilder::init(
    SearchAvailabilityFilterBuilder::init(
        TimeRangeBuilder::init()
            ->endAt('end_at6')
            ->startAt('start_at6')
            ->build()
    )
        ->bookingId('booking_id8')
        ->locationId('location_id8')
        ->segmentFilters(
            [
                SegmentFilterBuilder::init(
                    'service_variation_id4'
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
                    ->build(),
                SegmentFilterBuilder::init(
                    'service_variation_id4'
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
                    ->build(),
                SegmentFilterBuilder::init(
                    'service_variation_id4'
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
                    ->build()
            ]
        )
        ->build()
)->build();
```

