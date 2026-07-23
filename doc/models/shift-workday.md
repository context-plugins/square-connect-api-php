
# Shift Workday

A `Shift` search query filter parameter that sets a range of days that
a `Shift` must start or end in before passing the filter condition.

## Structure

`ShiftWorkday`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `dateRange` | [`?DateRange`](../../doc/models/date-range.md) | Optional | A range defined by two dates. Used for filtering a query for Connect v2<br>objects that have date properties. | getDateRange(): ?DateRange | setDateRange(?DateRange dateRange): void |
| `defaultTimezone` | `?string` | Optional | Location-specific timezones convert workdays to datetime filters.<br>Every location included in the query must have a timezone or this field<br>must be provided as a fallback. Format: the IANA timezone database<br>identifier for the relevant timezone. | getDefaultTimezone(): ?string | setDefaultTimezone(?string defaultTimezone): void |
| `matchShiftsBy` | `?string` | Optional | The strategy on which the dates are applied. | getMatchShiftsBy(): ?string | setMatchShiftsBy(?string matchShiftsBy): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\ShiftWorkdayBuilder;
use SquareConnectAPILib\Models\Builders\DateRangeBuilder;

$shiftWorkday = ShiftWorkdayBuilder::init()
    ->dateRange(
        DateRangeBuilder::init()
            ->endDate('end_date2')
            ->startDate('start_date6')
            ->build()
    )
    ->defaultTimezone('default_timezone8')
    ->matchShiftsBy('match_shifts_by6')
    ->build();
```

