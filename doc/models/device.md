
# Device

## Structure

`Device`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The device's Square-issued ID. | getId(): ?string | setId(?string id): void |
| `name` | `?string` | Optional | The device's merchant-specified name. | getName(): ?string | setName(?string name): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\DeviceBuilder;

$device = DeviceBuilder::init()
    ->id('id6')
    ->name('name6')
    ->build();
```

