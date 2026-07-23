
# Catalog Query Items for Modifier List

The query filter to return the items containing the specified modifier list IDs.

## Structure

`CatalogQueryItemsForModifierList`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `modifierListIds` | `string[]` | Required | A set of `CatalogModifierList` IDs to be used to find associated `CatalogItem`s. | getModifierListIds(): array | setModifierListIds(array modifierListIds): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CatalogQueryItemsForModifierListBuilder;

$catalogQueryItemsForModifierList = CatalogQueryItemsForModifierListBuilder::init(
    [
        'modifier_list_ids6'
    ]
)->build();
```

