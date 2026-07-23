
# Cash Drawer Device

## Structure

`CashDrawerDevice`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The device Square-issued ID | getId(): ?string | setId(?string id): void |
| `name` | `?string` | Optional | The device merchant-specified name. | getName(): ?string | setName(?string name): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CashDrawerDeviceBuilder;

$cashDrawerDevice = CashDrawerDeviceBuilder::init()
    ->id('id8')
    ->name('name8')
    ->build();
```

