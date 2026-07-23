
# Search Terminal Checkouts Response

## Structure

`SearchTerminalCheckoutsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `checkouts` | [`?(TerminalCheckout[])`](../../doc/models/terminal-checkout.md) | Optional | The requested search result of `TerminalCheckout` objects. | getCheckouts(): ?array | setCheckouts(?array checkouts): void |
| `cursor` | `?string` | Optional | The pagination cursor to be used in a subsequent request. If empty,<br>this is the final response.<br><br>See [Pagination](https://developer.squareup.com/docs/basics/api101/pagination) for more information. | getCursor(): ?string | setCursor(?string cursor): void |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Information about errors encountered during the request. | getErrors(): ?array | setErrors(?array errors): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\SearchTerminalCheckoutsResponseBuilder;
use SquareConnectAPILib\Models\Builders\TerminalCheckoutBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;
use SquareConnectAPILib\Models\Builders\DeviceCheckoutOptionsBuilder;
use SquareConnectAPILib\Models\Builders\TipSettingsBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;

$searchTerminalCheckoutsResponse = SearchTerminalCheckoutsResponseBuilder::init()
    ->checkouts(
        [
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
                ->cancelReason('cancel_reason4')
                ->createdAt('2020-03-31T18:13:15.921Z')
                ->deadlineDuration('PT10M')
                ->id('tsQPvzwBpMqqO')
                ->note('A brief note')
                ->paymentIds(
                    [
                        'rXnhZzywrEk4vR6pw76fPZfgvaB'
                    ]
                )
                ->referenceId('id14467')
                ->status('COMPLETED')
                ->updatedAt('2020-03-31T18:13:52.725Z')
                ->build(),
            TerminalCheckoutBuilder::init(
                MoneyBuilder::init()
                    ->amount(2610)
                    ->currency('USD')
                    ->build(),
                DeviceCheckoutOptionsBuilder::init(
                    'dbb5d83a-7838-11ea-bc55-0242ac130003'
                )
                    ->skipReceiptScreen(true)
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
                ->cancelReason('cancel_reason4')
                ->createdAt('2020-03-31T18:08:31.882Z')
                ->deadlineDuration('PT10M')
                ->id('XlOPTgcEhrbqO')
                ->note('A brief note')
                ->paymentIds(
                    [
                        'VYBF861PaoKPP7Pih0TlbZiNvaB'
                    ]
                )
                ->referenceId('id41623')
                ->status('COMPLETED')
                ->updatedAt('2020-03-31T18:08:41.635Z')
                ->build()
        ]
    )
    ->cursor('RiTJqBoTuXlbLmmrPvEkX9iG7XnQ4W4RjGnH')
    ->errors(
        [
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

