
# Shift

A record of the hourly rate, start, and end times for a single work shift
for an employee. This might include a record of the start and end times for breaks
taken during the shift.

## Structure

`Shift`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `breaks` | [`?(MBreak[])`](../../doc/models/m-break.md) | Optional | A list of all the paid or unpaid breaks that were taken during this shift. | getBreaks(): ?array | setBreaks(?array breaks): void |
| `createdAt` | `?string` | Optional | A read-only timestamp in RFC 3339 format; presented in UTC. | getCreatedAt(): ?string | setCreatedAt(?string createdAt): void |
| `employeeId` | `?string` | Optional | The ID of the employee this shift belongs to. DEPRECATED at version 2020-08-26. Use `team_member_id` instead. | getEmployeeId(): ?string | setEmployeeId(?string employeeId): void |
| `endAt` | `?string` | Optional | RFC 3339; shifted to the timezone + offset. Precision up to the minute is<br>respected; seconds are truncated. | getEndAt(): ?string | setEndAt(?string endAt): void |
| `id` | `?string` | Optional | The UUID for this object.<br><br>**Constraints**: *Maximum Length*: `255` | getId(): ?string | setId(?string id): void |
| `locationId` | `?string` | Optional | The ID of the location this shift occurred at. The location should be based on<br>where the employee clocked in. | getLocationId(): ?string | setLocationId(?string locationId): void |
| `startAt` | `string` | Required | RFC 3339; shifted to the location timezone + offset. Precision up to the<br>minute is respected; seconds are truncated.<br><br>**Constraints**: *Minimum Length*: `1` | getStartAt(): string | setStartAt(string startAt): void |
| `status` | `?string` | Optional | Describes the working state of the current `Shift`. | getStatus(): ?string | setStatus(?string status): void |
| `teamMemberId` | `?string` | Optional | The ID of the team member this shift belongs to. Replaced `employee_id` at version "2020-08-26". | getTeamMemberId(): ?string | setTeamMemberId(?string teamMemberId): void |
| `timezone` | `?string` | Optional | The read-only convenience value that is calculated from the location based<br>on the `location_id`. Format: the IANA timezone database identifier for the<br>location timezone. | getTimezone(): ?string | setTimezone(?string timezone): void |
| `updatedAt` | `?string` | Optional | A read-only timestamp in RFC 3339 format; presented in UTC. | getUpdatedAt(): ?string | setUpdatedAt(?string updatedAt): void |
| `version` | `?int` | Optional | Used for resolving concurrency issues. The request fails if the version<br>provided does not match the server version at the time of the request. If not provided,<br>Square executes a blind write; potentially overwriting data from another<br>write. | getVersion(): ?int | setVersion(?int version): void |
| `wage` | [`?ShiftWage`](../../doc/models/shift-wage.md) | Optional | The hourly wage rate used to compensate an employee for this shift. | getWage(): ?ShiftWage | setWage(?ShiftWage wage): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\ShiftBuilder;
use SquareConnectAPILib\Models\Builders\MBreakBuilder;

$shift = ShiftBuilder::init(
    'start_at6'
)
    ->breaks(
        [
            MBreakBuilder::init(
                'break_type_id2',
                'expected_duration8',
                false,
                'name6',
                'start_at8'
            )
                ->endAt('end_at4')
                ->id('id6')
                ->build(),
            MBreakBuilder::init(
                'break_type_id2',
                'expected_duration8',
                false,
                'name6',
                'start_at8'
            )
                ->endAt('end_at4')
                ->id('id6')
                ->build(),
            MBreakBuilder::init(
                'break_type_id2',
                'expected_duration8',
                false,
                'name6',
                'start_at8'
            )
                ->endAt('end_at4')
                ->id('id6')
                ->build()
        ]
    )
    ->createdAt('created_at2')
    ->employeeId('employee_id4')
    ->endAt('end_at6')
    ->id('id4')
    ->build();
```

