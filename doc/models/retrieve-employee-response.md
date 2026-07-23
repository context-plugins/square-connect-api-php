
# Retrieve Employee Response

## Structure

`RetrieveEmployeeResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `employee` | [`?Employee`](../../doc/models/employee.md) | Optional | An employee object that is used by the external API. | getEmployee(): ?Employee | setEmployee(?Employee employee): void |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\RetrieveEmployeeResponseBuilder;
use SquareConnectAPILib\Models\Builders\EmployeeBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;

$retrieveEmployeeResponse = RetrieveEmployeeResponseBuilder::init()
    ->employee(
        EmployeeBuilder::init()
            ->createdAt('created_at6')
            ->email('email8')
            ->firstName('first_name8')
            ->id('id8')
            ->isOwner(false)
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

