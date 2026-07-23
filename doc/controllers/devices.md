# Devices

```php
$devicesController = $client->getDevicesController();
```

## Class Name

`DevicesController`

## Methods

* [List Device Codes](../../doc/controllers/devices.md#list-device-codes)
* [Create Device Code](../../doc/controllers/devices.md#create-device-code)
* [Get Device Code](../../doc/controllers/devices.md#get-device-code)


# List Device Codes

Lists all DeviceCodes associated with the merchant.

```php
function listDeviceCodes(
    ?string $cursor = null,
    ?string $locationId = null,
    ?string $productType = null,
    ?string $status = null
): ListDeviceCodesResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `cursor` | `?string` | Query, Optional | A pagination cursor returned by a previous call to this endpoint.<br>Provide this to retrieve the next set of results for your original query.<br><br>See [Paginating results](https://developer.squareup.com/docs/working-with-apis/pagination) for more information. |
| `locationId` | `?string` | Query, Optional | If specified, only returns DeviceCodes of the specified location.<br>Returns DeviceCodes of all locations if empty. |
| `productType` | `?string` | Query, Optional | If specified, only returns DeviceCodes targeting the specified product type.<br>Returns DeviceCodes of all product types if empty. |
| `status` | `?string` | Query, Optional | If specified, returns DeviceCodes with the specified statuses.<br>Returns DeviceCodes of status `PAIRED` and `UNPAIRED` if empty. |

## Requires scope

### oauth2

`DEVICE_CREDENTIAL_MANAGEMENT`

## Response Type

**200**: Success

[`ListDeviceCodesResponse`](../../doc/models/list-device-codes-response.md)

## Example Usage

```php
$devicesController = $client->getDevicesController();

try {
    $result = $devicesController->listDeviceCodes();
    echo 'ListDeviceCodesResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Create Device Code

Creates a DeviceCode that can be used to login to a Square Terminal device to enter the connected
terminal mode.

```php
function createDeviceCode(CreateDeviceCodeRequest $body): CreateDeviceCodeResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`CreateDeviceCodeRequest`](../../doc/models/create-device-code-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`DEVICE_CREDENTIAL_MANAGEMENT`

## Response Type

**200**: Success

[`CreateDeviceCodeResponse`](../../doc/models/create-device-code-response.md)

## Example Usage

```php
$body = CreateDeviceCodeRequestBuilder::init(
    DeviceCodeBuilder::init(
        'product_type0'
    )->build(),
    'idempotency_key2'
)->build();

$devicesController = $client->getDevicesController();

try {
    $result = $devicesController->createDeviceCode($body);
    echo 'CreateDeviceCodeResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Get Device Code

Retrieves DeviceCode with the associated ID.

```php
function getDeviceCode(string $id): GetDeviceCodeResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The unique identifier for the device code. |

## Requires scope

### oauth2

`DEVICE_CREDENTIAL_MANAGEMENT`

## Response Type

**200**: Success

[`GetDeviceCodeResponse`](../../doc/models/get-device-code-response.md)

## Example Usage

```php
$id = 'id0';

$devicesController = $client->getDevicesController();

try {
    $result = $devicesController->getDeviceCode($id);
    echo 'GetDeviceCodeResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

