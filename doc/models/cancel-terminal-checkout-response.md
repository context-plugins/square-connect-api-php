
# Cancel Terminal Checkout Response

## Structure

`CancelTerminalCheckoutResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `checkout` | [`?TerminalCheckout`](../../doc/models/terminal-checkout.md) | Optional | - | getCheckout(): ?TerminalCheckout | setCheckout(?TerminalCheckout checkout): void |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Information about errors encountered during the request. | getErrors(): ?array | setErrors(?array errors): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CancelTerminalCheckoutResponseBuilder;
use SquareConnectAPILib\Models\Builders\TerminalCheckoutBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;
use SquareConnectAPILib\Models\Builders\DeviceCheckoutOptionsBuilder;
use SquareConnectAPILib\Models\Builders\TipSettingsBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;

$cancelTerminalCheckoutResponse = CancelTerminalCheckoutResponseBuilder::init()
    ->checkout(
        TerminalCheckoutBuilder::init(
            MoneyBuilder::init()
                ->amount(123)
                ->currency('USD')
                ->build(),
            DeviceCheckoutOptionsBuilder::init(
                'dbb5d83a-7838-11ea-bc55-0242ac130003'
            )
                ->skipReceiptScreen(true)
                ->tipSettings(
                    TipSettingsBuilder::init()
                        ->allowTipping(true)
                        ->customTipField(false)
                        ->separateTipScreen(false)
                        ->smartTipping(false)
                        ->tipPercentages(
                            [
                                48
                            ]
                        )
                        ->build()
                )
                ->build()
        )
            ->appId('APP_ID')
            ->cancelReason('SELLER_CANCELED')
            ->createdAt('2020-03-16T15:31:19.934Z')
            ->deadlineDuration('PT10M')
            ->id('S1yDlPQx7slqO')
            ->referenceId('id36815')
            ->status('CANCELED')
            ->updatedAt('2020-03-16T15:31:45.787Z')
            ->build()
    )
    ->errors(
        [
            ErrorBuilder::init(
                'category8',
                'code8'
            )
                ->detail('detail6')
                ->field('field4')
                ->build(),
            ErrorBuilder::init(
                'category8',
                'code8'
            )
                ->detail('detail6')
                ->field('field4')
                ->build()
        ]
    )
    ->build();
```

