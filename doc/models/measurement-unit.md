
# Measurement Unit

Represents a unit of measurement to use with a quantity, such as ounces
or inches. Exactly one of the following fields are required: `custom_unit`,
`area_unit`, `length_unit`, `volume_unit`, and `weight_unit`.

## Structure

`MeasurementUnit`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `areaUnit` | `?string` | Optional | Represents a standard area unit. | getAreaUnit(): ?string | setAreaUnit(?string areaUnit): void |
| `customUnit` | [`?MeasurementUnitCustom`](../../doc/models/measurement-unit-custom.md) | Optional | The information needed to define a custom unit, provided by the seller. | getCustomUnit(): ?MeasurementUnitCustom | setCustomUnit(?MeasurementUnitCustom customUnit): void |
| `genericUnit` | `?string` | Optional | Reserved for API integrations that lack the ability to specify a real measurement unit | getGenericUnit(): ?string | setGenericUnit(?string genericUnit): void |
| `lengthUnit` | `?string` | Optional | Represents a standard length unit. | getLengthUnit(): ?string | setLengthUnit(?string lengthUnit): void |
| `timeUnit` | `?string` | Optional | Represents a standard unit of time. | getTimeUnit(): ?string | setTimeUnit(?string timeUnit): void |
| `type` | `?string` | Optional | Represents the type of the measurement unit. | getType(): ?string | setType(?string type): void |
| `volumeUnit` | `?string` | Optional | Represents a standard volume unit. | getVolumeUnit(): ?string | setVolumeUnit(?string volumeUnit): void |
| `weightUnit` | `?string` | Optional | Represents a standard unit of weight or mass. | getWeightUnit(): ?string | setWeightUnit(?string weightUnit): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\MeasurementUnitBuilder;
use SquareConnectAPILib\Models\Builders\MeasurementUnitCustomBuilder;

$measurementUnit = MeasurementUnitBuilder::init()
    ->areaUnit('area_unit6')
    ->customUnit(
        MeasurementUnitCustomBuilder::init(
            'abbreviation4',
            'name2'
        )->build()
    )
    ->genericUnit('generic_unit2')
    ->lengthUnit('length_unit2')
    ->timeUnit('time_unit8')
    ->build();
```

