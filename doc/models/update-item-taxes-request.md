
# Update Item Taxes Request

## Structure

`UpdateItemTaxesRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `itemIds` | `string[]` | Required | IDs for the CatalogItems associated with the CatalogTax objects being updated. | getItemIds(): array | setItemIds(array itemIds): void |
| `taxesToDisable` | `?(string[])` | Optional | IDs of the CatalogTax objects to disable. | getTaxesToDisable(): ?array | setTaxesToDisable(?array taxesToDisable): void |
| `taxesToEnable` | `?(string[])` | Optional | IDs of the CatalogTax objects to enable. | getTaxesToEnable(): ?array | setTaxesToEnable(?array taxesToEnable): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\UpdateItemTaxesRequestBuilder;

$updateItemTaxesRequest = UpdateItemTaxesRequestBuilder::init(
    [
        'item_ids2',
        'item_ids3',
        'item_ids4'
    ]
)
    ->taxesToDisable(
        [
            'taxes_to_disable8'
        ]
    )
    ->taxesToEnable(
        [
            'taxes_to_enable8',
            'taxes_to_enable9'
        ]
    )
    ->build();
```

