
# Standard Unit Description Group

Group of standard measurement units.

## Structure

`StandardUnitDescriptionGroup`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `languageCode` | `?string` | Optional | IETF language tag. | getLanguageCode(): ?string | setLanguageCode(?string languageCode): void |
| `standardUnitDescriptions` | [`?(StandardUnitDescription[])`](../../doc/models/standard-unit-description.md) | Optional | List of standard (non-custom) measurement units in this description group. | getStandardUnitDescriptions(): ?array | setStandardUnitDescriptions(?array standardUnitDescriptions): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\StandardUnitDescriptionGroupBuilder;
use SquareConnectAPILib\Models\Builders\StandardUnitDescriptionBuilder;
use SquareConnectAPILib\Models\Builders\MeasurementUnitBuilder;
use SquareConnectAPILib\Models\Builders\MeasurementUnitCustomBuilder;

$standardUnitDescriptionGroup = StandardUnitDescriptionGroupBuilder::init()
    ->languageCode('language_code6')
    ->standardUnitDescriptions(
        [
            StandardUnitDescriptionBuilder::init()
                ->abbreviation('abbreviation6')
                ->name('name4')
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
                ->build(),
            StandardUnitDescriptionBuilder::init()
                ->abbreviation('abbreviation6')
                ->name('name4')
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
                ->build(),
            StandardUnitDescriptionBuilder::init()
                ->abbreviation('abbreviation6')
                ->name('name4')
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
                ->build()
        ]
    )
    ->build();
```

