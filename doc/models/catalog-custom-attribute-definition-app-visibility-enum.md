
# Catalog Custom Attribute Definition App Visibility Enum

Defines the visibility of a custom attribute to applications other than their
creating application.

## Enumeration

`CatalogCustomAttributeDefinitionAppVisibilityEnum`

## Fields

| Name | Description |
|  --- | --- |
| `APP_VISIBILITY_HIDDEN` | Other applications cannot read this custom attribute. |
| `APP_VISIBILITY_READ_ONLY` | Other applications can read this custom attribute definition and<br>values. |
| `APP_VISIBILITY_READ_WRITE_VALUES` | Other applications can read and write custom attribute values on objects.<br>They can read but cannot edit the custom attribute definition. |

## Example

```php
use SquareConnectAPILib\Models\CatalogCustomAttributeDefinitionAppVisibilityEnum;

$catalogCustomAttributeDefinitionAppVisibility = CatalogCustomAttributeDefinitionAppVisibilityEnum::APP_VISIBILITY_HIDDEN;
```

