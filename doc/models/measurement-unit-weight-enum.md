
# Measurement Unit Weight Enum

Unit of weight used to measure a quantity.

## Enumeration

`MeasurementUnitWeightEnum`

## Fields

| Name | Description |
|  --- | --- |
| `IMPERIAL_WEIGHT_OUNCE` | The weight is measured in ounces. |
| `IMPERIAL_POUND` | The weight is measured in pounds. |
| `IMPERIAL_STONE` | The weight is measured in stones. |
| `METRIC_MILLIGRAM` | The weight is measured in milligrams. |
| `METRIC_GRAM` | The weight is measured in grams. |
| `METRIC_KILOGRAM` | The weight is measured in kilograms. |

## Example

```php
use SquareConnectAPILib\Models\MeasurementUnitWeightEnum;

$measurementUnitWeight = MeasurementUnitWeightEnum::IMPERIAL_STONE;
```

