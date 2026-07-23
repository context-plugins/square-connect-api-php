
# Measurement Unit Time Enum

Unit of time used to measure a quantity (a duration).

## Enumeration

`MeasurementUnitTimeEnum`

## Fields

| Name | Description |
|  --- | --- |
| `GENERIC_MILLISECOND` | The time is measured in milliseconds. |
| `GENERIC_SECOND` | The time is measured in seconds. |
| `GENERIC_MINUTE` | The time is measured in minutes. |
| `GENERIC_HOUR` | The time is measured in hours. |
| `GENERIC_DAY` | The time is measured in days. |

## Example

```php
use SquareConnectAPILib\Models\MeasurementUnitTimeEnum;

$measurementUnitTime = MeasurementUnitTimeEnum::GENERIC_MINUTE;
```

