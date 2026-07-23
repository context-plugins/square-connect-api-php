
# Business Appointment Settings Max Appointments per Day Limit Type Enum

Types of daily appointment limits.

## Enumeration

`BusinessAppointmentSettingsMaxAppointmentsPerDayLimitTypeEnum`

## Fields

| Name | Description |
|  --- | --- |
| `PER_TEAM_MEMBER` | The maximum number of daily appointments is set on a per team member basis. |
| `PER_LOCATION` | The maximum number of daily appointments is set on a per location basis. |

## Example

```php
use SquareConnectAPILib\Models\BusinessAppointmentSettingsMaxAppointmentsPerDayLimitTypeEnum;

$businessAppointmentSettingsMaxAppointmentsPerDayLimitType = BusinessAppointmentSettingsMaxAppointmentsPerDayLimitTypeEnum::PER_TEAM_MEMBER;
```

