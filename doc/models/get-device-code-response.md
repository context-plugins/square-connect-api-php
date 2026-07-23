
# Get Device Code Response

## Structure

`GetDeviceCodeResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `deviceCode` | [`?DeviceCode`](../../doc/models/device-code.md) | Optional | - | getDeviceCode(): ?DeviceCode | setDeviceCode(?DeviceCode deviceCode): void |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\GetDeviceCodeResponseBuilder;
use SquareConnectAPILib\Models\Builders\DeviceCodeBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;

$getDeviceCodeResponse = GetDeviceCodeResponseBuilder::init()
    ->deviceCode(
        DeviceCodeBuilder::init(
            'TERMINAL_API'
        )
            ->code('EBCARJ')
            ->createdAt('2020-02-06T18:44:33.000Z')
            ->deviceId('907CS13101300122')
            ->id('B3Z6NAMYQSMTM')
            ->locationId('B5E4484SHHNYH')
            ->name('Counter 1')
            ->pairBy('2020-02-06T18:49:33.000Z')
            ->status('PAIRED')
            ->statusChangedAt('2020-02-06T18:47:28.000Z')
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
                ->build()
        ]
    )
    ->build();
```

