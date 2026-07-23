
# V1 Create Employee Role Request

## Structure

`V1CreateEmployeeRoleRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `employeeRole` | [`?V1EmployeeRole`](../../doc/models/v1-employee-role.md) | Optional | V1EmployeeRole | getEmployeeRole(): ?V1EmployeeRole | setEmployeeRole(?V1EmployeeRole employeeRole): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\V1CreateEmployeeRoleRequestBuilder;
use SquareConnectAPILib\Models\Builders\V1EmployeeRoleBuilder;

$v1CreateEmployeeRoleRequest = V1CreateEmployeeRoleRequestBuilder::init()
    ->employeeRole(
        V1EmployeeRoleBuilder::init(
            'name2',
            [
                'permissions9'
            ]
        )
            ->createdAt('created_at0')
            ->id('id2')
            ->isOwner(false)
            ->updatedAt('updated_at8')
            ->build()
    )
    ->build();
```

