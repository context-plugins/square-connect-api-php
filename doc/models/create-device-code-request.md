
# Create Device Code Request

## Structure

`CreateDeviceCodeRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `deviceCode` | [`DeviceCode`](../../doc/models/device-code.md) | Required | - | getDeviceCode(): DeviceCode | setDeviceCode(DeviceCode deviceCode): void |
| `idempotencyKey` | `string` | Required | A unique string that identifies this CreateDeviceCode request. Keys can<br>be any valid string but must be unique for every CreateDeviceCode request.<br><br>See [Idempotency keys](https://developer.squareup.com/docs/basics/api101/idempotency) for more information.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `128` | getIdempotencyKey(): string | setIdempotencyKey(string idempotencyKey): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CreateDeviceCodeRequestBuilder;
use SquareConnectAPILib\Models\Builders\DeviceCodeBuilder;

$createDeviceCodeRequest = CreateDeviceCodeRequestBuilder::init(
    DeviceCodeBuilder::init(
        'product_type0'
    )
        ->code('code2')
        ->createdAt('created_at2')
        ->deviceId('device_id0')
        ->id('id4')
        ->locationId('location_id8')
        ->build(),
    'idempotency_key0'
)->build();
```

