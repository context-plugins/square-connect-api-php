# Locations

```php
$locationsController = $client->getLocationsController();
```

## Class Name

`LocationsController`

## Methods

* [List Locations](../../doc/controllers/locations.md#list-locations)
* [Create Location](../../doc/controllers/locations.md#create-location)
* [Retrieve Location](../../doc/controllers/locations.md#retrieve-location)
* [Update Location](../../doc/controllers/locations.md#update-location)


# List Locations

Provides information of all locations of a business.

Many Square API endpoints require a `location_id` parameter.
The `id` field of the [`Location`](https://developer.squareup.com/reference/square_2021-08-18/objects/Location) objects returned by this
endpoint correspond to that `location_id` parameter.

```php
function listLocations(): ListLocationsResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Requires scope

### oauth2

`MERCHANT_PROFILE_READ`

## Response Type

**200**: Success

[`ListLocationsResponse`](../../doc/models/list-locations-response.md)

## Example Usage

```php
$locationsController = $client->getLocationsController();

try {
    $result = $locationsController->listLocations();
    echo 'ListLocationsResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Create Location

Creates a location.

```php
function createLocation(CreateLocationRequest $body): CreateLocationResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`CreateLocationRequest`](../../doc/models/create-location-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`MERCHANT_PROFILE_WRITE`

## Response Type

**200**: Success

[`CreateLocationResponse`](../../doc/models/create-location-response.md)

## Example Usage

```php
$body = CreateLocationRequestBuilder::init()->build();

$locationsController = $client->getLocationsController();

try {
    $result = $locationsController->createLocation($body);
    echo 'CreateLocationResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Retrieve Location

Retrieves details of a location. You can specify "main"
as the location ID to retrieve details of the
main location.

```php
function retrieveLocation(string $locationId): RetrieveLocationResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `locationId` | `string` | Template, Required | The ID of the location to retrieve. If you specify the string "main",<br>then the endpoint returns the main location. |

## Requires scope

### oauth2

`MERCHANT_PROFILE_READ`

## Response Type

**200**: Success

[`RetrieveLocationResponse`](../../doc/models/retrieve-location-response.md)

## Example Usage

```php
$locationId = 'location_id4';

$locationsController = $client->getLocationsController();

try {
    $result = $locationsController->retrieveLocation($locationId);
    echo 'RetrieveLocationResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Update Location

Updates a location.

```php
function updateLocation(string $locationId, UpdateLocationRequest $body): UpdateLocationResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `locationId` | `string` | Template, Required | The ID of the location to update. |
| `body` | [`UpdateLocationRequest`](../../doc/models/update-location-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`MERCHANT_PROFILE_WRITE`

## Response Type

**200**: Success

[`UpdateLocationResponse`](../../doc/models/update-location-response.md)

## Example Usage

```php
$locationId = 'location_id4';

$body = UpdateLocationRequestBuilder::init()->build();

$locationsController = $client->getLocationsController();

try {
    $result = $locationsController->updateLocation(
        $locationId,
        $body
    );
    echo 'UpdateLocationResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

