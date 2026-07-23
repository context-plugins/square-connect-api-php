
# Catalog Query Items for Tax

The query filter to return the items containing the specified tax IDs.

## Structure

`CatalogQueryItemsForTax`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `taxIds` | `string[]` | Required | A set of `CatalogTax` IDs to be used to find associated `CatalogItem`s. | getTaxIds(): array | setTaxIds(array taxIds): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CatalogQueryItemsForTaxBuilder;

$catalogQueryItemsForTax = CatalogQueryItemsForTaxBuilder::init(
    [
        'tax_ids7',
        'tax_ids6',
        'tax_ids5'
    ]
)->build();
```

