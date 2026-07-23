
# List Employee Wages Response

The response to a request for a set of `EmployeeWage` objects. The response contains
a set of `EmployeeWage` objects.

## Structure

`ListEmployeeWagesResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cursor` | `?string` | Optional | The value supplied in the subsequent request to fetch the next page<br>of `EmployeeWage` results. | getCursor(): ?string | setCursor(?string cursor): void |
| `employeeWages` | [`?(EmployeeWage[])`](../../doc/models/employee-wage.md) | Optional | A page of `EmployeeWage` results. | getEmployeeWages(): ?array | setEmployeeWages(?array employeeWages): void |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\ListEmployeeWagesResponseBuilder;
use SquareConnectAPILib\Models\Builders\EmployeeWageBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;

$listEmployeeWagesResponse = ListEmployeeWagesResponseBuilder::init()
    ->cursor('2fofTniCgT0yIPAq26kmk0YyFQJZfbWkh73OOnlTHmTAx13NgED')
    ->employeeWages(
        [
            EmployeeWageBuilder::init()
                ->employeeId('33fJchumvVdJwxV0H6L9')
                ->hourlyRate(
                    MoneyBuilder::init()
                        ->amount(3250)
                        ->currency('USD')
                        ->build()
                )
                ->id('pXS3qCv7BERPnEGedM4S8mhm')
                ->title('Manager')
                ->build(),
            EmployeeWageBuilder::init()
                ->employeeId('33fJchumvVdJwxV0H6L9')
                ->hourlyRate(
                    MoneyBuilder::init()
                        ->amount(2600)
                        ->currency('USD')
                        ->build()
                )
                ->id('rZduCkzYDUVL3ovh1sQgbue6')
                ->title('Cook')
                ->build(),
            EmployeeWageBuilder::init()
                ->employeeId('33fJchumvVdJwxV0H6L9')
                ->hourlyRate(
                    MoneyBuilder::init()
                        ->amount(1600)
                        ->currency('USD')
                        ->build()
                )
                ->id('FxLbs5KpPUHa8wyt5ctjubDX')
                ->title('Barista')
                ->build(),
            EmployeeWageBuilder::init()
                ->employeeId('33fJchumvVdJwxV0H6L9')
                ->hourlyRate(
                    MoneyBuilder::init()
                        ->amount(1700)
                        ->currency('USD')
                        ->build()
                )
                ->id('vD1wCgijMDR3cX5TPnu7VXto')
                ->title('Cashier')
                ->build()
        ]
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

