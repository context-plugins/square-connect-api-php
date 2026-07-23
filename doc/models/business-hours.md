
# Business Hours

Represents the hours of operation for a business location.

## Structure

`BusinessHours`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `periods` | [`?(BusinessHoursPeriod[])`](../../doc/models/business-hours-period.md) | Optional | The list of time periods during which the business is open. There may be at most 10<br>periods per day. | getPeriods(): ?array | setPeriods(?array periods): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\BusinessHoursBuilder;
use SquareConnectAPILib\Models\Builders\BusinessHoursPeriodBuilder;

$businessHours = BusinessHoursBuilder::init()
    ->periods(
        [
            BusinessHoursPeriodBuilder::init()
                ->dayOfWeek('day_of_week2')
                ->endLocalTime('end_local_time6')
                ->startLocalTime('start_local_time4')
                ->build(),
            BusinessHoursPeriodBuilder::init()
                ->dayOfWeek('day_of_week2')
                ->endLocalTime('end_local_time6')
                ->startLocalTime('start_local_time4')
                ->build(),
            BusinessHoursPeriodBuilder::init()
                ->dayOfWeek('day_of_week2')
                ->endLocalTime('end_local_time6')
                ->startLocalTime('start_local_time4')
                ->build()
        ]
    )
    ->build();
```

