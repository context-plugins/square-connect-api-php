
# Shift Query

The parameters of a `Shift` search query, which includes filter and sort options.

## Structure

`ShiftQuery`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `filter` | [`?ShiftFilter`](../../doc/models/shift-filter.md) | Optional | Defines a filter used in a search for `Shift` records. `AND` logic is<br>used by Square's servers to apply each filter property specified. | getFilter(): ?ShiftFilter | setFilter(?ShiftFilter filter): void |
| `sort` | [`?ShiftSort`](../../doc/models/shift-sort.md) | Optional | Sets the sort order of search results. | getSort(): ?ShiftSort | setSort(?ShiftSort sort): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\ShiftQueryBuilder;
use SquareConnectAPILib\Models\Builders\ShiftFilterBuilder;
use SquareConnectAPILib\Models\Builders\TimeRangeBuilder;
use SquareConnectAPILib\Models\Builders\ShiftWorkdayBuilder;
use SquareConnectAPILib\Models\Builders\DateRangeBuilder;
use SquareConnectAPILib\Models\Builders\ShiftSortBuilder;

$shiftQuery = ShiftQueryBuilder::init()
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
    ->build();
```

