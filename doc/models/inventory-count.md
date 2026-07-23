
# Inventory Count

Represents Square-estimated quantity of items in a particular state at a
particular seller location based on the known history of physical counts and
inventory adjustments.

## Structure

`InventoryCount`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `calculatedAt` | `?string` | Optional | An RFC 3339-formatted timestamp that indicates when the most recent physical count or adjustment affecting<br>the estimated count is received.<br><br>**Constraints**: *Maximum Length*: `34` | getCalculatedAt(): ?string | setCalculatedAt(?string calculatedAt): void |
| `catalogObjectId` | `?string` | Optional | The Square-generated ID of the<br>[CatalogObject](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogObject) being tracked.<br><br>**Constraints**: *Maximum Length*: `100` | getCatalogObjectId(): ?string | setCatalogObjectId(?string catalogObjectId): void |
| `catalogObjectType` | `?string` | Optional | The [type](https://developer.squareup.com/reference/square_2021-08-18/enums/CatalogObjectType) of the<br>[CatalogObject](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogObject) being tracked. Tracking is only<br>supported for the `ITEM_VARIATION` type.<br><br>**Constraints**: *Maximum Length*: `14` | getCatalogObjectType(): ?string | setCatalogObjectType(?string catalogObjectType): void |
| `isEstimated` | `?bool` | Optional | Whether the inventory count is for composed variation (TRUE) or not (FALSE). If true, the inventory count will not be present in the response of<br>any of these endpoints: [BatchChangeInventory](https://developer.squareup.com/reference/square_2021-08-18/inventory-api/batch-change-inventory),<br>[BatchRetrieveInventoryChanges](https://developer.squareup.com/reference/square_2021-08-18/inventory-api/batch-retrieve-inventory-changes),<br>[BatchRetrieveInventoryCounts](https://developer.squareup.com/reference/square_2021-08-18/inventory-api/batch-retrieve-inventory-counts), and<br>[RetrieveInventoryChanges](https://developer.squareup.com/reference/square_2021-08-18/inventory-api/retrieve-inventory-changes). | getIsEstimated(): ?bool | setIsEstimated(?bool isEstimated): void |
| `locationId` | `?string` | Optional | The Square-generated ID of the [Location](https://developer.squareup.com/reference/square_2021-08-18/objects/Location) where the related<br>quantity of items is being tracked.<br><br>**Constraints**: *Maximum Length*: `100` | getLocationId(): ?string | setLocationId(?string locationId): void |
| `quantity` | `?string` | Optional | The number of items affected by the estimated count as a decimal string.<br>Can support up to 5 digits after the decimal point.<br><br>**Constraints**: *Maximum Length*: `26` | getQuantity(): ?string | setQuantity(?string quantity): void |
| `state` | `?string` | Optional | The current [inventory state](https://developer.squareup.com/reference/square_2021-08-18/enums/InventoryState) for the related<br>quantity of items. | getState(): ?string | setState(?string state): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\InventoryCountBuilder;

$inventoryCount = InventoryCountBuilder::init()
    ->calculatedAt('calculated_at8')
    ->catalogObjectId('catalog_object_id0')
    ->catalogObjectType('catalog_object_type0')
    ->isEstimated(false)
    ->locationId('location_id0')
    ->build();
```

