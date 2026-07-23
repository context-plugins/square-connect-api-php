
# Batch Change Inventory Request

## Structure

`BatchChangeInventoryRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `changes` | [`?(InventoryChange[])`](../../doc/models/inventory-change.md) | Optional | The set of physical counts and inventory adjustments to be made.<br>Changes are applied based on the client-supplied timestamp and may be sent<br>out of order. | getChanges(): ?array | setChanges(?array changes): void |
| `idempotencyKey` | `string` | Required | A client-supplied, universally unique identifier (UUID) for the<br>request.<br><br>See [Idempotency](https://developer.squareup.com/docs/basics/api101/idempotency) in the<br>[API Development 101](https://developer.squareup.com/docs/basics/api101/overview) section for more<br>information.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `128` | getIdempotencyKey(): string | setIdempotencyKey(string idempotencyKey): void |
| `ignoreUnchangedCounts` | `?bool` | Optional | Indicates whether the current physical count should be ignored if<br>the quantity is unchanged since the last physical count. Default: `true`. | getIgnoreUnchangedCounts(): ?bool | setIgnoreUnchangedCounts(?bool ignoreUnchangedCounts): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\BatchChangeInventoryRequestBuilder;
use SquareConnectAPILib\Models\Builders\InventoryChangeBuilder;
use SquareConnectAPILib\Models\Builders\InventoryAdjustmentBuilder;
use SquareConnectAPILib\Models\Builders\InventoryAdjustmentGroupBuilder;
use SquareConnectAPILib\Models\Builders\CatalogMeasurementUnitBuilder;
use SquareConnectAPILib\Models\Builders\MeasurementUnitBuilder;
use SquareConnectAPILib\Models\Builders\MeasurementUnitCustomBuilder;
use SquareConnectAPILib\Models\Builders\InventoryPhysicalCountBuilder;
use SquareConnectAPILib\Models\Builders\InventoryTransferBuilder;

$batchChangeInventoryRequest = BatchChangeInventoryRequestBuilder::init(
    'idempotency_key2'
)
    ->changes(
        [
            InventoryChangeBuilder::init()
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
                ->measurementUnitId('measurement_unit_id8')
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
                ->build(),
            InventoryChangeBuilder::init()
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
                ->measurementUnitId('measurement_unit_id8')
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
                ->build()
        ]
    )
    ->ignoreUnchangedCounts(false)
    ->build();
```

