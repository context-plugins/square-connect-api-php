
# Shift Filter

Defines a filter used in a search for `Shift` records. `AND` logic is
used by Square's servers to apply each filter property specified.

## Structure

`ShiftFilter`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `employeeIds` | `?(string[])` | Optional | Fetch shifts for the specified employees. DEPRECATED at version 2020-08-26. Use `team_member_ids` instead. | getEmployeeIds(): ?array | setEmployeeIds(?array employeeIds): void |
| `end` | [`?TimeRange`](../../doc/models/time-range.md) | Optional | Represents a generic time range. The start and end values are<br>represented in RFC 3339 format. Time ranges are customized to be<br>inclusive or exclusive based on the needs of a particular endpoint.<br>Refer to the relevant endpoint-specific documentation to determine<br>how time ranges are handled. | getEnd(): ?TimeRange | setEnd(?TimeRange end): void |
| `locationIds` | `string[]` | Required | Fetch shifts for the specified location.<br><br>**Constraints**: *Minimum Length*: `1` | getLocationIds(): array | setLocationIds(array locationIds): void |
| `start` | [`?TimeRange`](../../doc/models/time-range.md) | Optional | Represents a generic time range. The start and end values are<br>represented in RFC 3339 format. Time ranges are customized to be<br>inclusive or exclusive based on the needs of a particular endpoint.<br>Refer to the relevant endpoint-specific documentation to determine<br>how time ranges are handled. | getStart(): ?TimeRange | setStart(?TimeRange start): void |
| `status` | `?string` | Optional | Fetch a `Shift` instance by `Shift.status`. | getStatus(): ?string | setStatus(?string status): void |
| `teamMemberIds` | `string[]` | Required | Fetch shifts for the specified team members. Replaced `employee_ids` at version "2020-08-26".<br><br>**Constraints**: *Minimum Length*: `1` | getTeamMemberIds(): array | setTeamMemberIds(array teamMemberIds): void |
| `workday` | [`?ShiftWorkday`](../../doc/models/shift-workday.md) | Optional | A `Shift` search query filter parameter that sets a range of days that<br>a `Shift` must start or end in before passing the filter condition. | getWorkday(): ?ShiftWorkday | setWorkday(?ShiftWorkday workday): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\ShiftFilterBuilder;
use SquareConnectAPILib\Models\Builders\TimeRangeBuilder;
use SquareConnectAPILib\Models\Builders\ShiftWorkdayBuilder;
use SquareConnectAPILib\Models\Builders\DateRangeBuilder;

$shiftFilter = ShiftFilterBuilder::init(
    [
        'location_ids0',
        'location_ids1',
        'location_ids2'
    ],
    [
        'team_member_ids7'
    ]
)
    ->employeeIds(
        [
            'employee_ids5',
            'employee_ids6',
            'employee_ids7'
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
    ->status('status2')
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
    ->build();
```

