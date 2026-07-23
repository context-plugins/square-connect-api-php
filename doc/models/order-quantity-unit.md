
# Order Quantity Unit

Contains the measurement unit for a quantity and a precision that
specifies the number of digits after the decimal point for decimal quantities.

## Structure

`OrderQuantityUnit`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `catalogVersion` | `?int` | Optional | The version of the catalog object that this measurement unit references.<br><br>This field is set when this is a catalog-backed measurement unit. | getCatalogVersion(): ?int | setCatalogVersion(?int catalogVersion): void |
| `measurementUnit` | [`?MeasurementUnit`](../../doc/models/measurement-unit.md) | Optional | Represents a unit of measurement to use with a quantity, such as ounces<br>or inches. Exactly one of the following fields are required: `custom_unit`,<br>`area_unit`, `length_unit`, `volume_unit`, and `weight_unit`. | getMeasurementUnit(): ?MeasurementUnit | setMeasurementUnit(?MeasurementUnit measurementUnit): void |
| `precision` | `?int` | Optional | For non-integer quantities, represents the number of digits after the decimal point that are<br>recorded for this quantity.<br><br>For example, a precision of 1 allows quantities such as `"1.0"` and `"1.1"`, but not `"1.01"`.<br><br>Min: 0. Max: 5. | getPrecision(): ?int | setPrecision(?int precision): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\OrderQuantityUnitBuilder;
use SquareConnectAPILib\Models\Builders\MeasurementUnitBuilder;
use SquareConnectAPILib\Models\Builders\MeasurementUnitCustomBuilder;

$orderQuantityUnit = OrderQuantityUnitBuilder::init()
    ->catalogVersion(52)
    ->measurementUnit(
        MeasurementUnitBuilder::init()
            ->areaUnit('area_unit6')
            ->customUnit(
                MeasurementUnitCustomBuilder::init(
                    'abbreviation4',
                    'name2'
                )->build()
            )
            ->genericUnit('generic_unit8')
            ->lengthUnit('length_unit2')
            ->timeUnit('time_unit2')
            ->build()
    )
    ->precision(14)
    ->build();
```

