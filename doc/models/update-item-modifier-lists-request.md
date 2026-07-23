
# Update Item Modifier Lists Request

## Structure

`UpdateItemModifierListsRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `itemIds` | `string[]` | Required | The IDs of the catalog items associated with the CatalogModifierList objects being updated. | getItemIds(): array | setItemIds(array itemIds): void |
| `modifierListsToDisable` | `?(string[])` | Optional | The IDs of the CatalogModifierList objects to disable for the CatalogItem. | getModifierListsToDisable(): ?array | setModifierListsToDisable(?array modifierListsToDisable): void |
| `modifierListsToEnable` | `?(string[])` | Optional | The IDs of the CatalogModifierList objects to enable for the CatalogItem. | getModifierListsToEnable(): ?array | setModifierListsToEnable(?array modifierListsToEnable): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\UpdateItemModifierListsRequestBuilder;

$updateItemModifierListsRequest = UpdateItemModifierListsRequestBuilder::init(
    [
        'item_ids2',
        'item_ids1'
    ]
)
    ->modifierListsToDisable(
        [
            'modifier_lists_to_disable1'
        ]
    )
    ->modifierListsToEnable(
        [
            'modifier_lists_to_enable8',
            'modifier_lists_to_enable7'
        ]
    )
    ->build();
```

