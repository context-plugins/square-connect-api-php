
# Get Employee Wage Response

A response to a request to get an `EmployeeWage`. The response contains
the requested `EmployeeWage` objects and might contain a set of `Error` objects if
the request resulted in errors.

## Structure

`GetEmployeeWageResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `employeeWage` | [`?EmployeeWage`](../../doc/models/employee-wage.md) | Optional | The hourly wage rate that an employee earns on a `Shift` for doing the job<br>specified by the `title` property of this object. Deprecated at version 2020-08-26. Use `TeamMemberWage` instead. | getEmployeeWage(): ?EmployeeWage | setEmployeeWage(?EmployeeWage employeeWage): void |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\GetEmployeeWageResponseBuilder;
use SquareConnectAPILib\Models\Builders\EmployeeWageBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;

$getEmployeeWageResponse = GetEmployeeWageResponseBuilder::init()
    ->employeeWage(
        EmployeeWageBuilder::init()
            ->employeeId('33fJchumvVdJwxV0H6L9')
            ->hourlyRate(
                MoneyBuilder::init()
                    ->amount(2000)
                    ->currency('USD')
                    ->build()
            )
            ->id('pXS3qCv7BERPnEGedM4S8mhm')
            ->title('Manager')
            ->build()
    )
    ->errors(
        [
            ErrorBuilder::init(
                'category8',
                'code8'
            )
                ->detail('detail6')
                ->field('field4')
                ->build(),
            ErrorBuilder::init(
                'category8',
                'code8'
            )
                ->detail('detail6')
                ->field('field4')
                ->build()
        ]
    )
    ->build();
```

