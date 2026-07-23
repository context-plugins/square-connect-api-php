
# Retrieve Inventory Transfer Response

## Structure

`RetrieveInventoryTransferResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `transfer` | [`?InventoryTransfer`](../../doc/models/inventory-transfer.md) | Optional | Represents the transfer of a quantity of product inventory at a<br>particular time from one location to another. | getTransfer(): ?InventoryTransfer | setTransfer(?InventoryTransfer transfer): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\RetrieveInventoryTransferResponseBuilder;
use SquareConnectAPILib\Models\Builders\InventoryTransferBuilder;
use SquareConnectAPILib\Models\Builders\SourceApplicationBuilder;

$retrieveInventoryTransferResponse = RetrieveInventoryTransferResponseBuilder::init()
    ->errors(
        []
    )
    ->transfer(
        InventoryTransferBuilder::init()
            ->catalogObjectId('W62UWFY35CWMYGVWK6TWJDNI')
            ->catalogObjectType('ITEM_VARIATION')
            ->createdAt('2016-11-17T13:02:15.142Z')
            ->employeeId('LRK57NSQ5X7PUD05')
            ->fromLocationId('C6W5YS5QM06F5')
            ->id('UDMOEO78BG6GYWA2XDRYX3KB')
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
            ->state('IN_STOCK')
            ->toLocationId('59TNP9SA8VGDA')
            ->build()
    )
    ->build();
```

