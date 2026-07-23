
# V1 Update Employee Role Request

## Structure

`V1UpdateEmployeeRoleRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `body` | [`V1EmployeeRole`](../../doc/models/v1-employee-role.md) | Required | V1EmployeeRole | getBody(): V1EmployeeRole | setBody(V1EmployeeRole body): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\V1UpdateEmployeeRoleRequestBuilder;
use SquareConnectAPILib\Models\Builders\V1EmployeeRoleBuilder;

$v1UpdateEmployeeRoleRequest = V1UpdateEmployeeRoleRequestBuilder::init(
    V1EmployeeRoleBuilder::init(
        'name6',
        [
            'permissions3',
            'permissions4',
            'permissions5'
        ]
    )
        ->createdAt('created_at4')
        ->id('id6')
        ->isOwner(false)
        ->updatedAt('updated_at8')
        ->build()
)->build();
```

