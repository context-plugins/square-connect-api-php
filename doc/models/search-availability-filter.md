
# Search Availability Filter

A query filter to search for availabilities by.

## Structure

`SearchAvailabilityFilter`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `bookingId` | `?string` | Optional | The query expression to search for availabilities for an existing booking by matching the specified `booking_id` value.<br>This is commonly used to reschedule an appointment.<br>If this expression is specified, the `location_id` and `segment_filters` expressions are not allowed. | getBookingId(): ?string | setBookingId(?string bookingId): void |
| `locationId` | `?string` | Optional | The query expression to search for availabilities matching the specified seller location IDs.<br>This query expression is not applicable when `booking_id` is present. | getLocationId(): ?string | setLocationId(?string locationId): void |
| `segmentFilters` | [`?(SegmentFilter[])`](../../doc/models/segment-filter.md) | Optional | The list of segment filters to apply. A query with `n` segment filters returns availabilities with `n` segments per<br>availability. It is not applicable when `booking_id` is present. | getSegmentFilters(): ?array | setSegmentFilters(?array segmentFilters): void |
| `startAtRange` | [`TimeRange`](../../doc/models/time-range.md) | Required | Represents a generic time range. The start and end values are<br>represented in RFC 3339 format. Time ranges are customized to be<br>inclusive or exclusive based on the needs of a particular endpoint.<br>Refer to the relevant endpoint-specific documentation to determine<br>how time ranges are handled. | getStartAtRange(): TimeRange | setStartAtRange(TimeRange startAtRange): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\SearchAvailabilityFilterBuilder;
use SquareConnectAPILib\Models\Builders\TimeRangeBuilder;
use SquareConnectAPILib\Models\Builders\SegmentFilterBuilder;
use SquareConnectAPILib\Models\Builders\FilterValueBuilder;

$searchAvailabilityFilter = SearchAvailabilityFilterBuilder::init(
    TimeRangeBuilder::init()
        ->endAt('end_at6')
        ->startAt('start_at6')
        ->build()
)
    ->bookingId('booking_id2')
    ->locationId('location_id2')
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
    ->build();
```

