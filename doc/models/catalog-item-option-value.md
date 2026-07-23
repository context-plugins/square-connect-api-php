
# Catalog Item Option Value

An enumerated value that can link a
`CatalogItemVariation` to an item option as one of
its item option values.

## Structure

`CatalogItemOptionValue`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `color` | `?string` | Optional | The HTML-supported hex color for the item option (e.g., "#ff8d4e85").<br>Only displayed if `show_colors` is enabled on the parent `ItemOption`. When<br>left unset, `color` defaults to white ("#ffffff") when `show_colors` is<br>enabled on the parent `ItemOption`. | getColor(): ?string | setColor(?string color): void |
| `description` | `?string` | Optional | A human-readable description for the option value. This is a searchable attribute for use in applicable query filters. | getDescription(): ?string | setDescription(?string description): void |
| `itemOptionId` | `?string` | Optional | Unique ID of the associated item option. | getItemOptionId(): ?string | setItemOptionId(?string itemOptionId): void |
| `name` | `?string` | Optional | Name of this item option value. This is a searchable attribute for use in applicable query filters. | getName(): ?string | setName(?string name): void |
| `ordinal` | `?int` | Optional | Determines where this option value appears in a list of option values. | getOrdinal(): ?int | setOrdinal(?int ordinal): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CatalogItemOptionValueBuilder;

$catalogItemOptionValue = CatalogItemOptionValueBuilder::init()
    ->color('color6')
    ->description('description2')
    ->itemOptionId('item_option_id4')
    ->name('name2')
    ->ordinal(0)
    ->build();
```

