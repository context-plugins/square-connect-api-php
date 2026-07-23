
# Catalog Query Sorted Attribute

The query expression to specify the key to sort search results.

## Structure

`CatalogQuerySortedAttribute`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `attributeName` | `string` | Required | The attribute whose value is used as the sort key.<br><br>**Constraints**: *Minimum Length*: `1` | getAttributeName(): string | setAttributeName(string attributeName): void |
| `initialAttributeValue` | `?string` | Optional | The first attribute value to be returned by the query. Ascending sorts will return only<br>objects with this value or greater, while descending sorts will return only objects with this value<br>or less. If unset, start at the beginning (for ascending sorts) or end (for descending sorts). | getInitialAttributeValue(): ?string | setInitialAttributeValue(?string initialAttributeValue): void |
| `sortOrder` | `?string` | Optional | The desired sort order, `"ASC"` (ascending) or `"DESC"` (descending). | getSortOrder(): ?string | setSortOrder(?string sortOrder): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CatalogQuerySortedAttributeBuilder;

$catalogQuerySortedAttribute = CatalogQuerySortedAttributeBuilder::init(
    'attribute_name0'
)
    ->initialAttributeValue('initial_attribute_value2')
    ->sortOrder('sort_order4')
    ->build();
```

