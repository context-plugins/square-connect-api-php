
# Create Terminal Checkout Request

## Structure

`CreateTerminalCheckoutRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `checkout` | [`TerminalCheckout`](../../doc/models/terminal-checkout.md) | Required | - | getCheckout(): TerminalCheckout | setCheckout(TerminalCheckout checkout): void |
| `idempotencyKey` | `string` | Required | A unique string that identifies this `CreateCheckout` request. Keys can be any valid string but<br>must be unique for every `CreateCheckout` request.<br><br>See [Idempotency keys](https://developer.squareup.com/docs/basics/api101/idempotency) for more information.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `64` | getIdempotencyKey(): string | setIdempotencyKey(string idempotencyKey): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CreateTerminalCheckoutRequestBuilder;
use SquareConnectAPILib\Models\Builders\TerminalCheckoutBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;
use SquareConnectAPILib\Models\Builders\DeviceCheckoutOptionsBuilder;
use SquareConnectAPILib\Models\Builders\TipSettingsBuilder;

$createTerminalCheckoutRequest = CreateTerminalCheckoutRequestBuilder::init(
    TerminalCheckoutBuilder::init(
        MoneyBuilder::init()
            ->amount(186)
            ->currency('currency8')
            ->build(),
        DeviceCheckoutOptionsBuilder::init(
            'device_id6'
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
        ->appId('app_id4')
        ->cancelReason('cancel_reason8')
        ->createdAt('created_at0')
        ->deadlineDuration('deadline_duration6')
        ->id('id2')
        ->build(),
    'idempotency_key8'
)->build();
```

