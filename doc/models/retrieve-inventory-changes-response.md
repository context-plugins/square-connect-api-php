
# Retrieve Inventory Changes Response

## Structure

`RetrieveInventoryChangesResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `changes` | [`?(InventoryChange[])`](../../doc/models/inventory-change.md) | Optional | The set of inventory changes for the requested object and locations. | getChanges(): ?array | setChanges(?array changes): void |
| `cursor` | `?string` | Optional | The pagination cursor to be used in a subsequent request. If unset,<br>this is the final response.<br><br>See the [Pagination](https://developer.squareup.com/docs/working-with-apis/pagination) guide for more information. | getCursor(): ?string | setCursor(?string cursor): void |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\RetrieveInventoryChangesResponseBuilder;
use SquareConnectAPILib\Models\Builders\InventoryChangeBuilder;
use SquareConnectAPILib\Models\Builders\InventoryAdjustmentBuilder;
use SquareConnectAPILib\Models\Builders\InventoryAdjustmentGroupBuilder;
use SquareConnectAPILib\Models\Builders\SourceApplicationBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;
use SquareConnectAPILib\Models\Builders\CatalogMeasurementUnitBuilder;
use SquareConnectAPILib\Models\Builders\MeasurementUnitBuilder;
use SquareConnectAPILib\Models\Builders\MeasurementUnitCustomBuilder;
use SquareConnectAPILib\Models\Builders\InventoryPhysicalCountBuilder;
use SquareConnectAPILib\Models\Builders\InventoryTransferBuilder;

$retrieveInventoryChangesResponse = RetrieveInventoryChangesResponseBuilder::init()
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
                        ->catalogObjectId('W62UWFY35CWMYGVWK6TWJDNI')
                        ->catalogObjectType('ITEM_VARIATION')
                        ->createdAt('2016-11-16T22:25:24.878Z')
                        ->employeeId('AV7YRCGI2H1J5NQ8E1XIZCNA')
                        ->fromState('IN_STOCK')
                        ->id('OJKJIUANKLMLQANZADNPLKAD')
                        ->locationId('C6W5YS5QM06F5')
                        ->occurredAt('2016-11-16T22:25:24.878Z')
                        ->quantity('3')
                        ->referenceId('d8207693-168f-4b44-a2fd-a7ff533ddd26')
                        ->source(
                            SourceApplicationBuilder::init()
                                ->applicationId('416ff29c-86c4-4feb-b58c-9705f21f3ea0')
                                ->name('Square Point of Sale 4.37')
                                ->product('SQUARE_POS')
                                ->build()
                        )
                        ->toState('SOLD')
                        ->totalPriceMoney(
                            MoneyBuilder::init()
                                ->amount(5000)
                                ->currency('USD')
                                ->build()
                        )
                        ->transactionId('5APV6JYK1SNCZD11AND2RX1Z')
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
                ->type('ADJUSTMENT')
                ->build()
        ]
    )
    ->cursor('cursor4')
    ->errors(
        []
    )
    ->build();
```

