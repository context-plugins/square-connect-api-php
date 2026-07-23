
# List Employees Response

## Structure

`ListEmployeesResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cursor` | `?string` | Optional | The token to be used to retrieve the next page of results. | getCursor(): ?string | setCursor(?string cursor): void |
| `employees` | [`?(Employee[])`](../../doc/models/employee.md) | Optional | - | getEmployees(): ?array | setEmployees(?array employees): void |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\ListEmployeesResponseBuilder;
use SquareConnectAPILib\Models\Builders\EmployeeBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;

$listEmployeesResponse = ListEmployeesResponseBuilder::init()
    ->cursor('cursor4')
    ->employees(
        [
            EmployeeBuilder::init()
                ->createdAt('created_at2')
                ->email('email2')
                ->firstName('first_name4')
                ->id('id4')
                ->isOwner(false)
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

