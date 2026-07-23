
# Shift Status Enum

Enumerates the possible status of a `Shift`.

## Enumeration

`ShiftStatusEnum`

## Fields

| Name | Description |
|  --- | --- |
| `OPEN` | Employee started a work shift and the shift is not complete |
| `CLOSED` | Employee started and ended a work shift. |

## Example

```php
use SquareConnectAPILib\Models\ShiftStatusEnum;

$shiftStatus = ShiftStatusEnum::OPEN;
```

