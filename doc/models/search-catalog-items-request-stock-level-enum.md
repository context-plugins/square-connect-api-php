
# Search Catalog Items Request Stock Level Enum

Defines supported stock levels of the item inventory.

## Enumeration

`SearchCatalogItemsRequestStockLevelEnum`

## Fields

| Name | Description |
|  --- | --- |
| `OUT` | The item inventory is empty. |
| `LOW` | The item inventory is low. |

## Example

```php
use SquareConnectAPILib\Models\SearchCatalogItemsRequestStockLevelEnum;

$searchCatalogItemsRequestStockLevel = SearchCatalogItemsRequestStockLevelEnum::OUT;
```

