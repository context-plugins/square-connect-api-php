
# Retrieve Inventory Adjustment Response

## Structure

`RetrieveInventoryAdjustmentResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `adjustment` | [`?InventoryAdjustment`](../../doc/models/inventory-adjustment.md) | Optional | Represents a change in state or quantity of product inventory at a<br>particular time and location. | getAdjustment(): ?InventoryAdjustment | setAdjustment(?InventoryAdjustment adjustment): void |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\RetrieveInventoryAdjustmentResponseBuilder;
use SquareConnectAPILib\Models\Builders\InventoryAdjustmentBuilder;
use SquareConnectAPILib\Models\Builders\InventoryAdjustmentGroupBuilder;
use SquareConnectAPILib\Models\Builders\SourceApplicationBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;

$retrieveInventoryAdjustmentResponse = RetrieveInventoryAdjustmentResponseBuilder::init()
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
            ->createdAt('2016-11-17T13:02:15.142Z')
            ->employeeId('LRK57NSQ5X7PUD05')
            ->fromState('IN_STOCK')
            ->id('UDMOEO78BG6GYWA2XDRYX3KB')
            ->locationId('C6W5YS5QM06F5')
            ->occurredAt('2016-11-16T25:44:22.837Z')
            ->quantity('7')
            ->referenceId('4a366069-4096-47a2-99a5-0084ac879509')
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
                    ->amount(4550)
                    ->currency('USD')
                    ->build()
            )
            ->build()
    )
    ->errors(
        []
    )
    ->build();
```

