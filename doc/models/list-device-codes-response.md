
# List Device Codes Response

## Structure

`ListDeviceCodesResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cursor` | `?string` | Optional | A pagination cursor to retrieve the next set of results for your<br>original query to the endpoint. This value is present only if the request<br>succeeded and additional results are available.<br><br>See [Paginating results](https://developer.squareup.com/docs/working-with-apis/pagination) for more information. | getCursor(): ?string | setCursor(?string cursor): void |
| `deviceCodes` | [`?(DeviceCode[])`](../../doc/models/device-code.md) | Optional | The queried DeviceCode. | getDeviceCodes(): ?array | setDeviceCodes(?array deviceCodes): void |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\ListDeviceCodesResponseBuilder;
use SquareConnectAPILib\Models\Builders\DeviceCodeBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;

$listDeviceCodesResponse = ListDeviceCodesResponseBuilder::init()
    ->cursor('cursor2')
    ->deviceCodes(
        [
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
                ->build(),
            DeviceCodeBuilder::init(
                'TERMINAL_API'
            )
                ->code('GVXNYN')
                ->createdAt('2020-02-07T19:55:04.000Z')
                ->deviceId('device_id4')
                ->id('YKGMJMYK8H4PQ')
                ->locationId('A6SYFRSV4WAFW')
                ->name('Unused device code')
                ->pairBy('2020-02-07T20:00:04.000Z')
                ->status('UNPAIRED')
                ->statusChangedAt('2020-02-07T19:55:04.000Z')
                ->build()
        ]
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

