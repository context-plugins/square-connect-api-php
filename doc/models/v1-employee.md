
# V1 Employee

Represents one of a business's employees.

## Structure

`V1Employee`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `authorizedLocationIds` | `?(string[])` | Optional | The IDs of the locations the employee is allowed to clock in at. | getAuthorizedLocationIds(): ?array | setAuthorizedLocationIds(?array authorizedLocationIds): void |
| `createdAt` | `?string` | Optional | The time when the employee entity was created, in ISO 8601 format. | getCreatedAt(): ?string | setCreatedAt(?string createdAt): void |
| `email` | `?string` | Optional | The employee's email address. | getEmail(): ?string | setEmail(?string email): void |
| `externalId` | `?string` | Optional | An ID the merchant can set to associate the employee with an entity in another system. | getExternalId(): ?string | setExternalId(?string externalId): void |
| `firstName` | `string` | Required | The employee's first name. | getFirstName(): string | setFirstName(string firstName): void |
| `id` | `?string` | Optional | The employee's unique ID. | getId(): ?string | setId(?string id): void |
| `lastName` | `string` | Required | The employee's last name. | getLastName(): string | setLastName(string lastName): void |
| `roleIds` | `?(string[])` | Optional | The ids of the employee's associated roles. Currently, you can specify only one or zero roles per employee. | getRoleIds(): ?array | setRoleIds(?array roleIds): void |
| `status` | `?string` | Optional | Whether the employee is ACTIVE or INACTIVE. Inactive employees cannot sign in to Square Register.Merchants update this field from the Square Dashboard. | getStatus(): ?string | setStatus(?string status): void |
| `updatedAt` | `?string` | Optional | The time when the employee entity was most recently updated, in ISO 8601 format. | getUpdatedAt(): ?string | setUpdatedAt(?string updatedAt): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\V1EmployeeBuilder;

$v1Employee = V1EmployeeBuilder::init(
    'first_name2',
    'last_name0'
)
    ->authorizedLocationIds(
        [
            'authorized_location_ids3',
            'authorized_location_ids4'
        ]
    )
    ->createdAt('created_at0')
    ->email('email4')
    ->externalId('external_id8')
    ->id('id2')
    ->build();
```

