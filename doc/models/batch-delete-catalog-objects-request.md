
# Batch Delete Catalog Objects Request

## Structure

`BatchDeleteCatalogObjectsRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `objectIds` | `?(string[])` | Optional | The IDs of the CatalogObjects to be deleted. When an object is deleted, other objects<br>in the graph that depend on that object will be deleted as well (for example, deleting a<br>CatalogItem will delete its CatalogItemVariation. | getObjectIds(): ?array | setObjectIds(?array objectIds): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\BatchDeleteCatalogObjectsRequestBuilder;

$batchDeleteCatalogObjectsRequest = BatchDeleteCatalogObjectsRequestBuilder::init()
    ->objectIds(
        [
            'object_ids4'
        ]
    )
    ->build();
```

