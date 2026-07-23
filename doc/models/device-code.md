
# Device Code

## Structure

`DeviceCode`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `code` | `?string` | Optional | The unique code that can be used to login. | getCode(): ?string | setCode(?string code): void |
| `createdAt` | `?string` | Optional | When this DeviceCode was created. Timestamp in RFC 3339 format. | getCreatedAt(): ?string | setCreatedAt(?string createdAt): void |
| `deviceId` | `?string` | Optional | The unique id of the device that used this code. Populated when the device is paired up. | getDeviceId(): ?string | setDeviceId(?string deviceId): void |
| `id` | `?string` | Optional | The unique id for this device code. | getId(): ?string | setId(?string id): void |
| `locationId` | `?string` | Optional | The location assigned to this code.<br><br>**Constraints**: *Maximum Length*: `50` | getLocationId(): ?string | setLocationId(?string locationId): void |
| `name` | `?string` | Optional | An optional user-defined name for the device code.<br><br>**Constraints**: *Maximum Length*: `128` | getName(): ?string | setName(?string name): void |
| `pairBy` | `?string` | Optional | When this DeviceCode will expire and no longer login. Timestamp in RFC 3339 format. | getPairBy(): ?string | setPairBy(?string pairBy): void |
| `pairedAt` | `?string` | Optional | When this DeviceCode was paired. Timestamp in RFC 3339 format. | getPairedAt(): ?string | setPairedAt(?string pairedAt): void |
| `productType` | `string` | Required | The targeting product type of the device code. | getProductType(): string | setProductType(string productType): void |
| `status` | `?string` | Optional | The pairing status of the device code. | getStatus(): ?string | setStatus(?string status): void |
| `statusChangedAt` | `?string` | Optional | When this DeviceCode's status was last changed. Timestamp in RFC 3339 format. | getStatusChangedAt(): ?string | setStatusChangedAt(?string statusChangedAt): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\DeviceCodeBuilder;

$deviceCode = DeviceCodeBuilder::init(
    'product_type4'
)
    ->code('code6')
    ->createdAt('created_at6')
    ->deviceId('device_id4')
    ->id('id8')
    ->locationId('location_id2')
    ->build();
```

