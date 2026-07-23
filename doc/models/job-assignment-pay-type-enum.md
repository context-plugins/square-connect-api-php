
# Job Assignment Pay Type Enum

Enumerates the possible pay types that a job can be assigned.

## Enumeration

`JobAssignmentPayTypeEnum`

## Fields

| Name | Description |
|  --- | --- |
| `NONE` | The job does not have a defined pay type. |
| `HOURLY` | The job pays an hourly rate. |
| `SALARY` | The job pays an annual salary. |

## Example

```php
use SquareConnectAPILib\Models\JobAssignmentPayTypeEnum;

$jobAssignmentPayType = JobAssignmentPayTypeEnum::SALARY;
```

