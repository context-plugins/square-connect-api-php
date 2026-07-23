
# Catalog Info Response

## Structure

`CatalogInfoResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `limits` | [`?CatalogInfoResponseLimits`](../../doc/models/catalog-info-response-limits.md) | Optional | - | getLimits(): ?CatalogInfoResponseLimits | setLimits(?CatalogInfoResponseLimits limits): void |
| `standardUnitDescriptionGroup` | [`?StandardUnitDescriptionGroup`](../../doc/models/standard-unit-description-group.md) | Optional | Group of standard measurement units. | getStandardUnitDescriptionGroup(): ?StandardUnitDescriptionGroup | setStandardUnitDescriptionGroup(?StandardUnitDescriptionGroup standardUnitDescriptionGroup): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CatalogInfoResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\CatalogInfoResponseLimitsBuilder;
use SquareConnectAPILib\Models\Builders\StandardUnitDescriptionGroupBuilder;
use SquareConnectAPILib\Models\Builders\StandardUnitDescriptionBuilder;
use SquareConnectAPILib\Models\Builders\MeasurementUnitBuilder;
use SquareConnectAPILib\Models\Builders\MeasurementUnitCustomBuilder;

$catalogInfoResponse = CatalogInfoResponseBuilder::init()
    ->errors(
        [
            ErrorBuilder::init(
                'category8',
                'code8'
            )
                ->detail('detail6')
                ->field('field4')
                ->build(),
            ErrorBuilder::init(
                'category8',
                'code8'
            )
                ->detail('detail6')
                ->field('field4')
                ->build()
        ]
    )
    ->limits(
        CatalogInfoResponseLimitsBuilder::init()
            ->batchDeleteMaxObjectIds(200)
            ->batchRetrieveMaxObjectIds(1000)
            ->batchUpsertMaxObjectsPerBatch(1000)
            ->batchUpsertMaxTotalObjects(10000)
            ->searchMaxPageLimit(1000)
            ->updateItemModifierListsMaxItemIds(1000)
            ->updateItemModifierListsMaxModifierListsToDisable(1000)
            ->updateItemModifierListsMaxModifierListsToEnable(1000)
            ->updateItemTaxesMaxItemIds(1000)
            ->updateItemTaxesMaxTaxesToDisable(1000)
            ->updateItemTaxesMaxTaxesToEnable(1000)
            ->build()
    )
    ->standardUnitDescriptionGroup(
        StandardUnitDescriptionGroupBuilder::init()
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
                        ->build()
                ]
            )
            ->build()
    )
    ->build();
```

