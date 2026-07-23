
# Cash Drawer Shift State Enum

The current state of a cash drawer shift.

## Enumeration

`CashDrawerShiftStateEnum`

## Fields

| Name | Description |
|  --- | --- |
| `OPEN` | An open cash drawer shift. |
| `ENDED` | A cash drawer shift that is ended but has not yet had an employee content audit. |
| `CLOSED` | An ended cash drawer shift that is closed with a completed employee<br>content audit and recorded result. |

## Example

```php
use SquareConnectAPILib\Models\CashDrawerShiftStateEnum;

$cashDrawerShiftState = CashDrawerShiftStateEnum::OPEN;
```

