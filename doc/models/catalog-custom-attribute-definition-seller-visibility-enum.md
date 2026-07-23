
# Catalog Custom Attribute Definition Seller Visibility Enum

Defines the visibility of a custom attribute to sellers in Square
client applications, Square APIs or in Square UIs (including Square Point
of Sale applications and Square Dashboard).

## Enumeration

`CatalogCustomAttributeDefinitionSellerVisibilityEnum`

## Fields

| Name | Description |
|  --- | --- |
| `SELLER_VISIBILITY_HIDDEN` | Sellers cannot read this custom attribute in Square client<br>applications or Square APIs. |
| `SELLER_VISIBILITY_READ_WRITE_VALUES` | Sellers can read and write this custom attribute value in catalog objects,<br>but cannot edit the custom attribute definition. |

## Example

```php
use SquareConnectAPILib\Models\CatalogCustomAttributeDefinitionSellerVisibilityEnum;

$catalogCustomAttributeDefinitionSellerVisibility = CatalogCustomAttributeDefinitionSellerVisibilityEnum::SELLER_VISIBILITY_HIDDEN;
```

