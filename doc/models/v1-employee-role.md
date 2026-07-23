
# V1 Employee Role

V1EmployeeRole

## Structure

`V1EmployeeRole`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `createdAt` | `?string` | Optional | The time when the employee entity was created, in ISO 8601 format. Is set by Square when the Role is created. | getCreatedAt(): ?string | setCreatedAt(?string createdAt): void |
| `id` | `?string` | Optional | The role's unique ID, Can only be set by Square. | getId(): ?string | setId(?string id): void |
| `isOwner` | `?bool` | Optional | If true, employees with this role have all permissions, regardless of the values indicated in permissions. | getIsOwner(): ?bool | setIsOwner(?bool isOwner): void |
| `name` | `string` | Required | The role's merchant-defined name. | getName(): string | setName(string name): void |
| `permissions` | `string[]` | Required | The role's permissions. | getPermissions(): array | setPermissions(array permissions): void |
| `updatedAt` | `?string` | Optional | The time when the employee entity was most recently updated, in ISO 8601 format. Is set by Square when the Role updated. | getUpdatedAt(): ?string | setUpdatedAt(?string updatedAt): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\V1EmployeeRoleBuilder;

$v1EmployeeRole = V1EmployeeRoleBuilder::init(
    'name4',
    [
        'permissions1'
    ]
)
    ->createdAt('created_at2')
    ->id('id4')
    ->isOwner(false)
    ->updatedAt('updated_at0')
    ->build();
```

