
# Business Hours Period

Represents a period of time during which a business location is open.

## Structure

`BusinessHoursPeriod`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `dayOfWeek` | `?string` | Optional | The day of week for this time period. | getDayOfWeek(): ?string | setDayOfWeek(?string dayOfWeek): void |
| `endLocalTime` | `?string` | Optional | The end time of a business hours period, specified in local time using partial-time<br>RFC 3339 format. | getEndLocalTime(): ?string | setEndLocalTime(?string endLocalTime): void |
| `startLocalTime` | `?string` | Optional | The start time of a business hours period, specified in local time using partial-time<br>RFC 3339 format. | getStartLocalTime(): ?string | setStartLocalTime(?string startLocalTime): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\BusinessHoursPeriodBuilder;

$businessHoursPeriod = BusinessHoursPeriodBuilder::init()
    ->dayOfWeek('day_of_week0')
    ->endLocalTime('end_local_time8')
    ->startLocalTime('start_local_time6')
    ->build();
```

