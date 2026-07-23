
# Shift Filter Status Enum

Specifies the `status` of `Shift` records to be returned.

## Enumeration

`ShiftFilterStatusEnum`

## Fields

| Name | Description |
|  --- | --- |
| `OPEN` | Shifts that have been started and not ended. |
| `CLOSED` | Shifts that have been started and ended. |

## Example

```php
use SquareConnectAPILib\Models\ShiftFilterStatusEnum;

$shiftFilterStatus = ShiftFilterStatusEnum::OPEN;
```

