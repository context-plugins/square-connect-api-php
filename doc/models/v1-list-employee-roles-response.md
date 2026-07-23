
# V1 List Employee Roles Response

## Structure

`V1ListEmployeeRolesResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `items` | [`?(V1EmployeeRole[])`](../../doc/models/v1-employee-role.md) | Optional | - | getItems(): ?array | setItems(?array items): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\V1ListEmployeeRolesResponseBuilder;
use SquareConnectAPILib\Models\Builders\V1EmployeeRoleBuilder;

$v1ListEmployeeRolesResponse = V1ListEmployeeRolesResponseBuilder::init()
    ->items(
        [
            V1EmployeeRoleBuilder::init(
                'name8',
                [
                    'permissions5',
                    'permissions6',
                    'permissions7'
                ]
            )
                ->createdAt('created_at6')
                ->id('id8')
                ->isOwner(false)
                ->updatedAt('updated_at6')
                ->build(),
            V1EmployeeRoleBuilder::init(
                'name8',
                [
                    'permissions5',
                    'permissions6',
                    'permissions7'
                ]
            )
                ->createdAt('created_at6')
                ->id('id8')
                ->isOwner(false)
                ->updatedAt('updated_at6')
                ->build()
        ]
    )
    ->build();
```

