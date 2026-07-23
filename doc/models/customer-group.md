
# Customer Group

Represents a group of customer profiles.

Customer groups can be created, be modified, and have their membership defined using
the Customers API or within the Customer Directory in the Square Seller Dashboard or Point of Sale.

## Structure

`CustomerGroup`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `createdAt` | `?string` | Optional | The timestamp when the customer group was created, in RFC 3339 format. | getCreatedAt(): ?string | setCreatedAt(?string createdAt): void |
| `id` | `?string` | Optional | A unique Square-generated ID for the customer group.<br><br>**Constraints**: *Maximum Length*: `255` | getId(): ?string | setId(?string id): void |
| `name` | `string` | Required | The name of the customer group. | getName(): string | setName(string name): void |
| `updatedAt` | `?string` | Optional | The timestamp when the customer group was last updated, in RFC 3339 format. | getUpdatedAt(): ?string | setUpdatedAt(?string updatedAt): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CustomerGroupBuilder;

$customerGroup = CustomerGroupBuilder::init(
    'name4'
)
    ->createdAt('created_at2')
    ->id('id4')
    ->updatedAt('updated_at0')
    ->build();
```

