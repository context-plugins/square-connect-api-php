
# Employee

An employee object that is used by the external API.

## Structure

`Employee`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `createdAt` | `?string` | Optional | A read-only timestamp in RFC 3339 format. | getCreatedAt(): ?string | setCreatedAt(?string createdAt): void |
| `email` | `?string` | Optional | The employee's email address | getEmail(): ?string | setEmail(?string email): void |
| `firstName` | `?string` | Optional | The employee's first name. | getFirstName(): ?string | setFirstName(?string firstName): void |
| `id` | `?string` | Optional | UUID for this object. | getId(): ?string | setId(?string id): void |
| `isOwner` | `?bool` | Optional | Whether this employee is the owner of the merchant. Each merchant<br>has one owner employee, and that employee has full authority over<br>the account. | getIsOwner(): ?bool | setIsOwner(?bool isOwner): void |
| `lastName` | `?string` | Optional | The employee's last name. | getLastName(): ?string | setLastName(?string lastName): void |
| `locationIds` | `?(string[])` | Optional | A list of location IDs where this employee has access to. | getLocationIds(): ?array | setLocationIds(?array locationIds): void |
| `phoneNumber` | `?string` | Optional | The employee's phone number in E.164 format, i.e. "+12125554250" | getPhoneNumber(): ?string | setPhoneNumber(?string phoneNumber): void |
| `status` | `?string` | Optional | Specifies the status of the employees being fetched. | getStatus(): ?string | setStatus(?string status): void |
| `updatedAt` | `?string` | Optional | A read-only timestamp in RFC 3339 format. | getUpdatedAt(): ?string | setUpdatedAt(?string updatedAt): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\EmployeeBuilder;

$employee = EmployeeBuilder::init()
    ->createdAt('created_at6')
    ->email('email8')
    ->firstName('first_name8')
    ->id('id8')
    ->isOwner(false)
    ->build();
```

