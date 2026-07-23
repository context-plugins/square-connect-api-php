
# Shift Workday Matcher Enum

Defines the logic used to apply a workday filter.

## Enumeration

`ShiftWorkdayMatcherEnum`

## Fields

| Name | Description |
|  --- | --- |
| `START_AT` | All shifts that start on or after the specified workday |
| `END_AT` | All shifts that end on or before the specified workday |
| `INTERSECTION` | All shifts that start between the start and end workdays (inclusive) |

## Example

```php
use SquareConnectAPILib\Models\ShiftWorkdayMatcherEnum;

$shiftWorkdayMatcher = ShiftWorkdayMatcherEnum::END_AT;
```

