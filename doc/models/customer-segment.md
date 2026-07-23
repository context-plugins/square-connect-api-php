
# Customer Segment

Represents a group of customer profiles that match one or more predefined filter criteria.

Segments (also known as Smart Groups) are defined and created within the Customer Directory in the
Square Seller Dashboard or Point of Sale.

## Structure

`CustomerSegment`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `createdAt` | `?string` | Optional | The timestamp when the segment was created, in RFC 3339 format. | getCreatedAt(): ?string | setCreatedAt(?string createdAt): void |
| `id` | `?string` | Optional | A unique Square-generated ID for the segment.<br><br>**Constraints**: *Maximum Length*: `255` | getId(): ?string | setId(?string id): void |
| `name` | `string` | Required | The name of the segment. | getName(): string | setName(string name): void |
| `updatedAt` | `?string` | Optional | The timestamp when the segment was last updated, in RFC 3339 format. | getUpdatedAt(): ?string | setUpdatedAt(?string updatedAt): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CustomerSegmentBuilder;

$customerSegment = CustomerSegmentBuilder::init(
    'name2'
)
    ->createdAt('created_at0')
    ->id('id2')
    ->updatedAt('updated_at2')
    ->build();
```

