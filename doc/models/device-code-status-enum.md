
# Device Code Status Enum

DeviceCode.Status enum.

## Enumeration

`DeviceCodeStatusEnum`

## Fields

| Name | Description |
|  --- | --- |
| `UNKNOWN` | The status cannot be determined or does not exist. |
| `UNPAIRED` | The device code is just created and unpaired. |
| `PAIRED` | The device code has been signed in and paired to a device. |
| `EXPIRED` | The device code was unpaired and expired before it was paired. |

## Example

```php
use SquareConnectAPILib\Models\DeviceCodeStatusEnum;

$deviceCodeStatus = DeviceCodeStatusEnum::UNKNOWN;
```

