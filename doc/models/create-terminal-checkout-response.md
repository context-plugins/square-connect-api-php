
# Create Terminal Checkout Response

## Structure

`CreateTerminalCheckoutResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `checkout` | [`?TerminalCheckout`](../../doc/models/terminal-checkout.md) | Optional | - | getCheckout(): ?TerminalCheckout | setCheckout(?TerminalCheckout checkout): void |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Information about errors encountered during the request. | getErrors(): ?array | setErrors(?array errors): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CreateTerminalCheckoutResponseBuilder;
use SquareConnectAPILib\Models\Builders\TerminalCheckoutBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;
use SquareConnectAPILib\Models\Builders\DeviceCheckoutOptionsBuilder;
use SquareConnectAPILib\Models\Builders\TipSettingsBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;

$createTerminalCheckoutResponse = CreateTerminalCheckoutResponseBuilder::init()
    ->checkout(
        TerminalCheckoutBuilder::init(
            MoneyBuilder::init()
                ->amount(2610)
                ->currency('USD')
                ->build(),
            DeviceCheckoutOptionsBuilder::init(
                'dbb5d83a-7838-11ea-bc55-0242ac130003'
            )
                ->skipReceiptScreen(false)
                ->tipSettings(
                    TipSettingsBuilder::init()
                        ->allowTipping(false)
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
            ->cancelReason('cancel_reason8')
            ->createdAt('2020-04-06T16:39:32.545Z')
            ->deadlineDuration('PT10M')
            ->id('08YceKh7B3ZqO')
            ->note('A brief note')
            ->paymentType('CARD_PRESENT')
            ->referenceId('id11572')
            ->status('PENDING')
            ->updatedAt('2020-04-06T16:39:32.545Z')
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

