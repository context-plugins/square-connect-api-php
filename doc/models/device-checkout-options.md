
# Device Checkout Options

## Structure

`DeviceCheckoutOptions`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `deviceId` | `string` | Required | The unique ID of the device intended for this `TerminalCheckout`.<br>A list of `DeviceCode` objects can be retrieved from the /v2/devices/codes endpoint.<br>Match a `DeviceCode.device_id` value with `device_id` to get the associated device code. | getDeviceId(): string | setDeviceId(string deviceId): void |
| `skipReceiptScreen` | `?bool` | Optional | Instructs the device to skip the receipt screen. Defaults to false. | getSkipReceiptScreen(): ?bool | setSkipReceiptScreen(?bool skipReceiptScreen): void |
| `tipSettings` | [`?TipSettings`](../../doc/models/tip-settings.md) | Optional | - | getTipSettings(): ?TipSettings | setTipSettings(?TipSettings tipSettings): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\DeviceCheckoutOptionsBuilder;
use SquareConnectAPILib\Models\Builders\TipSettingsBuilder;

$deviceCheckoutOptions = DeviceCheckoutOptionsBuilder::init(
    'device_id4'
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
    ->build();
```

