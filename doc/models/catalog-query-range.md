
# Catalog Query Range

The query filter to return the search result whose named attribute values fall between the specified range.

## Structure

`CatalogQueryRange`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `attributeMaxValue` | `?int` | Optional | The desired maximum value for the search attribute (inclusive). | getAttributeMaxValue(): ?int | setAttributeMaxValue(?int attributeMaxValue): void |
| `attributeMinValue` | `?int` | Optional | The desired minimum value for the search attribute (inclusive). | getAttributeMinValue(): ?int | setAttributeMinValue(?int attributeMinValue): void |
| `attributeName` | `string` | Required | The name of the attribute to be searched.<br><br>**Constraints**: *Minimum Length*: `1` | getAttributeName(): string | setAttributeName(string attributeName): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CatalogQueryRangeBuilder;

$catalogQueryRange = CatalogQueryRangeBuilder::init(
    'attribute_name8'
)
    ->attributeMaxValue(4)
    ->attributeMinValue(86)
    ->build();
```

