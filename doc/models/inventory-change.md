
# Inventory Change

Represents a single physical count, inventory, adjustment, or transfer
that is part of the history of inventory changes for a particular
[CatalogObject](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogObject) instance.

## Structure

`InventoryChange`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `adjustment` | [`?InventoryAdjustment`](../../doc/models/inventory-adjustment.md) | Optional | Represents a change in state or quantity of product inventory at a<br>particular time and location. | getAdjustment(): ?InventoryAdjustment | setAdjustment(?InventoryAdjustment adjustment): void |
| `measurementUnit` | [`?CatalogMeasurementUnit`](../../doc/models/catalog-measurement-unit.md) | Optional | Represents the unit used to measure a `CatalogItemVariation` and<br>specifies the precision for decimal quantities. | getMeasurementUnit(): ?CatalogMeasurementUnit | setMeasurementUnit(?CatalogMeasurementUnit measurementUnit): void |
| `measurementUnitId` | `?string` | Optional | The ID of the [CatalogMeasurementUnit](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogMeasurementUnit) object representing the catalog measurement unit associated with the inventory change. | getMeasurementUnitId(): ?string | setMeasurementUnitId(?string measurementUnitId): void |
| `physicalCount` | [`?InventoryPhysicalCount`](../../doc/models/inventory-physical-count.md) | Optional | Represents the quantity of an item variation that is physically present<br>at a specific location, verified by a seller or a seller's employee. For example,<br>a physical count might come from an employee counting the item variations on<br>hand or from syncing with an external system. | getPhysicalCount(): ?InventoryPhysicalCount | setPhysicalCount(?InventoryPhysicalCount physicalCount): void |
| `transfer` | [`?InventoryTransfer`](../../doc/models/inventory-transfer.md) | Optional | Represents the transfer of a quantity of product inventory at a<br>particular time from one location to another. | getTransfer(): ?InventoryTransfer | setTransfer(?InventoryTransfer transfer): void |
| `type` | `?string` | Optional | Indicates how the inventory change is applied. See<br>[InventoryChangeType](https://developer.squareup.com/reference/square_2021-08-18/enums/InventoryChangeType) for all possible values. | getType(): ?string | setType(?string type): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\InventoryChangeBuilder;
use SquareConnectAPILib\Models\Builders\InventoryAdjustmentBuilder;
use SquareConnectAPILib\Models\Builders\InventoryAdjustmentGroupBuilder;
use SquareConnectAPILib\Models\Builders\CatalogMeasurementUnitBuilder;
use SquareConnectAPILib\Models\Builders\MeasurementUnitBuilder;
use SquareConnectAPILib\Models\Builders\MeasurementUnitCustomBuilder;
use SquareConnectAPILib\Models\Builders\InventoryPhysicalCountBuilder;
use SquareConnectAPILib\Models\Builders\InventoryTransferBuilder;

$inventoryChange = InventoryChangeBuilder::init()
    ->adjustment(
        InventoryAdjustmentBuilder::init()
            ->adjustmentGroup(
                InventoryAdjustmentGroupBuilder::init()
                    ->fromState('from_state8')
                    ->id('id2')
                    ->rootAdjustmentId('root_adjustment_id2')
                    ->toState('to_state6')
                    ->build()
            )
            ->catalogObjectId('catalog_object_id8')
            ->catalogObjectType('catalog_object_type8')
            ->createdAt('created_at2')
            ->employeeId('employee_id4')
            ->build()
    )
    ->measurementUnit(
        CatalogMeasurementUnitBuilder::init()
            ->measurementUnit(
                MeasurementUnitBuilder::init()
                    ->areaUnit('area_unit6')
                    ->customUnit(
                        MeasurementUnitCustomBuilder::init(
                            'abbreviation4',
                            'name2'
                        )->build()
                    )
                    ->genericUnit('generic_unit8')
                    ->lengthUnit('length_unit2')
                    ->timeUnit('time_unit2')
                    ->build()
            )
            ->precision(184)
            ->build()
    )
    ->measurementUnitId('measurement_unit_id4')
    ->physicalCount(
        InventoryPhysicalCountBuilder::init()
            ->catalogObjectId('catalog_object_id6')
            ->catalogObjectType('catalog_object_type6')
            ->createdAt('created_at0')
            ->employeeId('employee_id2')
            ->id('id2')
            ->build()
    )
    ->transfer(
        InventoryTransferBuilder::init()
            ->catalogObjectId('catalog_object_id2')
            ->catalogObjectType('catalog_object_type2')
            ->createdAt('created_at6')
            ->employeeId('employee_id8')
            ->fromLocationId('from_location_id0')
            ->build()
    )
    ->build();
```

