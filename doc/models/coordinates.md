
# Coordinates

Latitude and longitude coordinates.

## Structure

`Coordinates`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `latitude` | `?float` | Optional | The latitude of the coordinate expressed in degrees. | getLatitude(): ?float | setLatitude(?float latitude): void |
| `longitude` | `?float` | Optional | The longitude of the coordinate expressed in degrees. | getLongitude(): ?float | setLongitude(?float longitude): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CoordinatesBuilder;

$coordinates = CoordinatesBuilder::init()
    ->latitude(39.14)
    ->longitude(36.94)
    ->build();
```

