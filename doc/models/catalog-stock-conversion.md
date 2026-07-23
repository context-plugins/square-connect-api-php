
# Catalog Stock Conversion

Represents the rule of conversion between a stockable [CatalogItemVariation](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogItemVariation)
and a non-stockable sell-by or receive-by `CatalogItemVariation` that
share the same underlying stock.

## Structure

`CatalogStockConversion`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `nonstockableQuantity` | `string` | Required | The converted equivalent quantity of the non-stockable [CatalogItemVariation](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogItemVariation)<br>in its measurement unit. The `stockable_quantity` value and this `nonstockable_quantity` value together<br>define the conversion ratio between stockable item variation and the non-stockable item variation.<br>It accepts a decimal number in a string format that can take up to 10 digits before the decimal point<br>and up to 5 digits after the decimal point.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `16` | getNonstockableQuantity(): string | setNonstockableQuantity(string nonstockableQuantity): void |
| `stockableItemVariationId` | `string` | Required | References to the stockable [CatalogItemVariation](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogItemVariation)<br>for this stock conversion. Selling, receiving or recounting the non-stockable `CatalogItemVariation`<br>defined with a stock conversion results in adjustments of this stockable `CatalogItemVariation`.<br>This immutable field must reference a stockable `CatalogItemVariation`<br>that shares the parent [CatalogItem](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogItem) of the converted `CatalogItemVariation.`<br><br>**Constraints**: *Minimum Length*: `1` | getStockableItemVariationId(): string | setStockableItemVariationId(string stockableItemVariationId): void |
| `stockableQuantity` | `string` | Required | The quantity of the stockable item variation (as identified by `stockable_item_variation_id`)<br>equivalent to the non-stockable item variation quantity (as specified in `nonstockable_quantity`)<br>as defined by this stock conversion.  It accepts a decimal number in a string format that can take<br>up to 10 digits before the decimal point and up to 5 digits after the decimal point.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `16` | getStockableQuantity(): string | setStockableQuantity(string stockableQuantity): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CatalogStockConversionBuilder;

$catalogStockConversion = CatalogStockConversionBuilder::init(
    'nonstockable_quantity0',
    'stockable_item_variation_id4',
    'stockable_quantity2'
)->build();
```

