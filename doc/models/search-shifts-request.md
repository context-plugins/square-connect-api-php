
# Search Shifts Request

A request for a filtered and sorted set of `Shift` objects.

## Structure

`SearchShiftsRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cursor` | `?string` | Optional | An opaque cursor for fetching the next page. | getCursor(): ?string | setCursor(?string cursor): void |
| `limit` | `?int` | Optional | The number of resources in a page (200 by default).<br><br>**Constraints**: `>= 1`, `<= 200` | getLimit(): ?int | setLimit(?int limit): void |
| `query` | [`?ShiftQuery`](../../doc/models/shift-query.md) | Optional | The parameters of a `Shift` search query, which includes filter and sort options. | getQuery(): ?ShiftQuery | setQuery(?ShiftQuery query): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\SearchShiftsRequestBuilder;
use SquareConnectAPILib\Models\Builders\ShiftQueryBuilder;
use SquareConnectAPILib\Models\Builders\ShiftFilterBuilder;
use SquareConnectAPILib\Models\Builders\TimeRangeBuilder;
use SquareConnectAPILib\Models\Builders\ShiftWorkdayBuilder;
use SquareConnectAPILib\Models\Builders\DateRangeBuilder;
use SquareConnectAPILib\Models\Builders\ShiftSortBuilder;

$searchShiftsRequest = SearchShiftsRequestBuilder::init()
    ->cursor('cursor6')
    ->limit(116)
    ->query(
        ShiftQueryBuilder::init()
            ->filter(
                ShiftFilterBuilder::init(
                    [
                        'location_ids4'
                    ],
                    [
                        'team_member_ids1',
                        'team_member_ids2'
                    ]
                )
                    ->employeeIds(
                        [
                            'employee_ids9'
                        ]
                    )
                    ->end(
                        TimeRangeBuilder::init()
                            ->endAt('end_at2')
                            ->startAt('start_at0')
                            ->build()
                    )
                    ->start(
                        TimeRangeBuilder::init()
                            ->endAt('end_at6')
                            ->startAt('start_at6')
                            ->build()
                    )
                    ->status('status6')
                    ->workday(
                        ShiftWorkdayBuilder::init()
                            ->dateRange(
                                DateRangeBuilder::init()
                                    ->endDate('end_date2')
                                    ->startDate('start_date6')
                                    ->build()
                            )
                            ->defaultTimezone('default_timezone0')
                            ->matchShiftsBy('match_shifts_by2')
                            ->build()
                    )
                    ->build()
            )
            ->sort(
                ShiftSortBuilder::init()
                    ->field('field2')
                    ->order('order8')
                    ->build()
            )
            ->build()
    )
    ->build();
```

