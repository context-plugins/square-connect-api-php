
# Standard Unit Description

Contains the name and abbreviation for standard measurement unit.

## Structure

`StandardUnitDescription`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `abbreviation` | `?string` | Optional | UI display abbreviation for the measurement unit. For example, 'lb'. | getAbbreviation(): ?string | setAbbreviation(?string abbreviation): void |
| `name` | `?string` | Optional | UI display name of the measurement unit. For example, 'Pound'. | getName(): ?string | setName(?string name): void |
| `unit` | [`?MeasurementUnit`](../../doc/models/measurement-unit.md) | Optional | Represents a unit of measurement to use with a quantity, such as ounces<br>or inches. Exactly one of the following fields are required: `custom_unit`,<br>`area_unit`, `length_unit`, `volume_unit`, and `weight_unit`. | getUnit(): ?MeasurementUnit | setUnit(?MeasurementUnit unit): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\StandardUnitDescriptionBuilder;
use SquareConnectAPILib\Models\Builders\MeasurementUnitBuilder;
use SquareConnectAPILib\Models\Builders\MeasurementUnitCustomBuilder;

$standardUnitDescription = StandardUnitDescriptionBuilder::init()
    ->abbreviation('abbreviation8')
    ->name('name6')
    ->unit(
        MeasurementUnitBuilder::init()
            ->areaUnit('area_unit4')
            ->customUnit(
                MeasurementUnitCustomBuilder::init(
                    'abbreviation4',
                    'name2'
                )->build()
            )
            ->genericUnit('generic_unit0')
            ->lengthUnit('length_unit4')
            ->timeUnit('time_unit4')
            ->build()
    )
    ->build();
```

