
# Device Details

Details about the device that took the payment.

## Structure

`DeviceDetails`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `deviceId` | `?string` | Optional | The Square-issued ID of the device.<br><br>**Constraints**: *Maximum Length*: `255` | getDeviceId(): ?string | setDeviceId(?string deviceId): void |
| `deviceInstallationId` | `?string` | Optional | The Square-issued installation ID for the device.<br><br>**Constraints**: *Maximum Length*: `255` | getDeviceInstallationId(): ?string | setDeviceInstallationId(?string deviceInstallationId): void |
| `deviceName` | `?string` | Optional | The name of the device set by the seller.<br><br>**Constraints**: *Maximum Length*: `255` | getDeviceName(): ?string | setDeviceName(?string deviceName): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\DeviceDetailsBuilder;

$deviceDetails = DeviceDetailsBuilder::init()
    ->deviceId('device_id0')
    ->deviceInstallationId('device_installation_id2')
    ->deviceName('device_name8')
    ->build();
```

