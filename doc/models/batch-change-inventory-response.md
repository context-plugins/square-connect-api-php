
# Batch Change Inventory Response

## Structure

`BatchChangeInventoryResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `changes` | [`?(InventoryChange[])`](../../doc/models/inventory-change.md) | Optional | Changes created for the request. | getChanges(): ?array | setChanges(?array changes): void |
| `counts` | [`?(InventoryCount[])`](../../doc/models/inventory-count.md) | Optional | The current counts for all objects referenced in the request. | getCounts(): ?array | setCounts(?array counts): void |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\BatchChangeInventoryResponseBuilder;
use SquareConnectAPILib\Models\Builders\InventoryChangeBuilder;
use SquareConnectAPILib\Models\Builders\InventoryAdjustmentBuilder;
use SquareConnectAPILib\Models\Builders\InventoryAdjustmentGroupBuilder;
use SquareConnectAPILib\Models\Builders\CatalogMeasurementUnitBuilder;
use SquareConnectAPILib\Models\Builders\MeasurementUnitBuilder;
use SquareConnectAPILib\Models\Builders\MeasurementUnitCustomBuilder;
use SquareConnectAPILib\Models\Builders\InventoryPhysicalCountBuilder;
use SquareConnectAPILib\Models\Builders\InventoryTransferBuilder;
use SquareConnectAPILib\Models\Builders\InventoryCountBuilder;

$batchChangeInventoryResponse = BatchChangeInventoryResponseBuilder::init()
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
    ->counts(
        [
            InventoryCountBuilder::init()
                ->calculatedAt('2016-11-16T22:28:01.223Z')
                ->catalogObjectId('W62UWFY35CWMYGVWK6TWJDNI')
                ->catalogObjectType('ITEM_VARIATION')
                ->isEstimated(false)
                ->locationId('C6W5YS5QM06F5')
                ->quantity('53')
                ->state('IN_STOCK')
                ->build()
        ]
    )
    ->errors(
        []
    )
    ->build();
```

