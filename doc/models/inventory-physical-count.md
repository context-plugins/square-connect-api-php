
# Inventory Physical Count

Represents the quantity of an item variation that is physically present
at a specific location, verified by a seller or a seller's employee. For example,
a physical count might come from an employee counting the item variations on
hand or from syncing with an external system.

## Structure

`InventoryPhysicalCount`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `catalogObjectId` | `?string` | Optional | The Square-generated ID of the<br>[CatalogObject](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogObject) being tracked.<br><br>**Constraints**: *Maximum Length*: `100` | getCatalogObjectId(): ?string | setCatalogObjectId(?string catalogObjectId): void |
| `catalogObjectType` | `?string` | Optional | The [type](https://developer.squareup.com/reference/square_2021-08-18/enums/CatalogObjectType) of the<br>[CatalogObject](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogObject) being tracked. Tracking is only<br>supported for the `ITEM_VARIATION` type.<br><br>**Constraints**: *Maximum Length*: `14` | getCatalogObjectType(): ?string | setCatalogObjectType(?string catalogObjectType): void |
| `createdAt` | `?string` | Optional | An RFC 3339-formatted timestamp that indicates when the physical count is received.<br><br>**Constraints**: *Maximum Length*: `34` | getCreatedAt(): ?string | setCreatedAt(?string createdAt): void |
| `employeeId` | `?string` | Optional | The Square-generated ID of the [Employee](https://developer.squareup.com/reference/square_2021-08-18/objects/Employee) responsible for the<br>physical count.<br><br>**Constraints**: *Maximum Length*: `100` | getEmployeeId(): ?string | setEmployeeId(?string employeeId): void |
| `id` | `?string` | Optional | A unique Square-generated ID for the<br>[InventoryPhysicalCount](https://developer.squareup.com/reference/square_2021-08-18/objects/InventoryPhysicalCount).<br><br>**Constraints**: *Maximum Length*: `100` | getId(): ?string | setId(?string id): void |
| `locationId` | `?string` | Optional | The Square-generated ID of the [Location](https://developer.squareup.com/reference/square_2021-08-18/objects/Location) where the related<br>quantity of items is being tracked.<br><br>**Constraints**: *Maximum Length*: `100` | getLocationId(): ?string | setLocationId(?string locationId): void |
| `occurredAt` | `?string` | Optional | A client-generated RFC 3339-formatted timestamp that indicates when<br>the physical count was examined. For physical count updates, the `occurred_at`<br>timestamp cannot be older than 24 hours or in the future relative to the<br>time of the request.<br><br>**Constraints**: *Maximum Length*: `34` | getOccurredAt(): ?string | setOccurredAt(?string occurredAt): void |
| `quantity` | `?string` | Optional | The number of items affected by the physical count as a decimal string.<br>The number can support up to 5 digits after the decimal point.<br><br>**Constraints**: *Maximum Length*: `26` | getQuantity(): ?string | setQuantity(?string quantity): void |
| `referenceId` | `?string` | Optional | An optional ID provided by the application to tie the<br>[InventoryPhysicalCount](https://developer.squareup.com/reference/square_2021-08-18/objects/InventoryPhysicalCount) to an external<br>system.<br><br>**Constraints**: *Maximum Length*: `255` | getReferenceId(): ?string | setReferenceId(?string referenceId): void |
| `source` | [`?SourceApplication`](../../doc/models/source-application.md) | Optional | Provides information about the application used to generate a change. | getSource(): ?SourceApplication | setSource(?SourceApplication source): void |
| `state` | `?string` | Optional | The current [inventory state](https://developer.squareup.com/reference/square_2021-08-18/enums/InventoryState) for the related<br>quantity of items. | getState(): ?string | setState(?string state): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\InventoryPhysicalCountBuilder;

$inventoryPhysicalCount = InventoryPhysicalCountBuilder::init()
    ->catalogObjectId('catalog_object_id6')
    ->catalogObjectType('catalog_object_type6')
    ->createdAt('created_at8')
    ->employeeId('employee_id0')
    ->id('id0')
    ->build();
```

