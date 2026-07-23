
# Catalog Query Exact

The query filter to return the search result by exact match of the specified attribute name and value.

## Structure

`CatalogQueryExact`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `attributeName` | `string` | Required | The name of the attribute to be searched. Matching of the attribute name is exact.<br><br>**Constraints**: *Minimum Length*: `1` | getAttributeName(): string | setAttributeName(string attributeName): void |
| `attributeValue` | `string` | Required | The desired value of the search attribute. Matching of the attribute value is case insensitive and can be partial.<br>For example, if a specified value of "sma", objects with the named attribute value of "Small", "small" are both matched. | getAttributeValue(): string | setAttributeValue(string attributeValue): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CatalogQueryExactBuilder;

$catalogQueryExact = CatalogQueryExactBuilder::init(
    'attribute_name6',
    'attribute_value4'
)->build();
```

