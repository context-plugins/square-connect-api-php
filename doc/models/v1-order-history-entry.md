
# V1 Order History Entry

V1OrderHistoryEntry

## Structure

`V1OrderHistoryEntry`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `action` | `?string` | Optional | The type of action performed on the order. | getAction(): ?string | setAction(?string action): void |
| `createdAt` | `?string` | Optional | The time when the action was performed, in ISO 8601 format. | getCreatedAt(): ?string | setCreatedAt(?string createdAt): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\V1OrderHistoryEntryBuilder;

$v1OrderHistoryEntry = V1OrderHistoryEntryBuilder::init()
    ->action('action0')
    ->createdAt('created_at0')
    ->build();
```

