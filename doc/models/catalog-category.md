
# Catalog Category

A category to which a `CatalogItem` instance belongs.

## Structure

`CatalogCategory`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `name` | `?string` | Optional | The category name. This is a searchable attribute for use in applicable query filters, and its value length is of Unicode code points.<br><br>**Constraints**: *Maximum Length*: `255` | getName(): ?string | setName(?string name): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CatalogCategoryBuilder;

$catalogCategory = CatalogCategoryBuilder::init()
    ->name('name6')
    ->build();
```

