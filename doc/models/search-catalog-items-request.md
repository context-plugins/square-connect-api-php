
# Search Catalog Items Request

Defines the request body for the [SearchCatalogItems](https://developer.squareup.com/reference/square_2021-08-18/catalog-api/search-catalog-items) endpoint.

## Structure

`SearchCatalogItemsRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `categoryIds` | `?(string[])` | Optional | The category id query expression to return items containing the specified category IDs. | getCategoryIds(): ?array | setCategoryIds(?array categoryIds): void |
| `cursor` | `?string` | Optional | The pagination token, returned in the previous response, used to fetch the next batch of pending results. | getCursor(): ?string | setCursor(?string cursor): void |
| `customAttributeFilters` | [`?(CustomAttributeFilter[])`](../../doc/models/custom-attribute-filter.md) | Optional | The customer-attribute filter to return items or item variations matching the specified<br>custom attribute expressions. A maximum number of 10 custom attribute expressions are supported in<br>a single call to the [SearchCatalogItems](https://developer.squareup.com/reference/square_2021-08-18/catalog-api/search-catalog-items) endpoint. | getCustomAttributeFilters(): ?array | setCustomAttributeFilters(?array customAttributeFilters): void |
| `enabledLocationIds` | `?(string[])` | Optional | The enabled-location query expression to return items and item variations having specified enabled locations. | getEnabledLocationIds(): ?array | setEnabledLocationIds(?array enabledLocationIds): void |
| `limit` | `?int` | Optional | The maximum number of results to return per page. The default value is 100.<br><br>**Constraints**: `<= 100` | getLimit(): ?int | setLimit(?int limit): void |
| `productTypes` | `?(string[])` | Optional | The product types query expression to return items or item variations having the specified product types. | getProductTypes(): ?array | setProductTypes(?array productTypes): void |
| `sortOrder` | `?string` | Optional | The order to sort the results by item names. The default sort order is ascending (`ASC`). | getSortOrder(): ?string | setSortOrder(?string sortOrder): void |
| `stockLevels` | `?(string[])` | Optional | The stock-level query expression to return item variations with the specified stock levels. | getStockLevels(): ?array | setStockLevels(?array stockLevels): void |
| `textFilter` | `?string` | Optional | The text filter expression to return items or item variations containing specified text in<br>the `name`, `description`, or `abbreviation` attribute value of an item, or in<br>the `name`, `sku`, or `upc` attribute value of an item variation. | getTextFilter(): ?string | setTextFilter(?string textFilter): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\SearchCatalogItemsRequestBuilder;
use SquareConnectAPILib\Models\Builders\CustomAttributeFilterBuilder;
use SquareConnectAPILib\Models\Builders\RangeBuilder;

$searchCatalogItemsRequest = SearchCatalogItemsRequestBuilder::init()
    ->categoryIds(
        [
            'category_ids7',
            'category_ids8',
            'category_ids9'
        ]
    )
    ->cursor('cursor8')
    ->customAttributeFilters(
        [
            CustomAttributeFilterBuilder::init()
                ->boolFilter(false)
                ->customAttributeDefinitionId('custom_attribute_definition_id6')
                ->key('key6')
                ->numberFilter(
                    RangeBuilder::init()
                        ->max('max4')
                        ->min('min8')
                        ->build()
                )
                ->selectionUidsFilter(
                    [
                        'selection_uids_filter6',
                        'selection_uids_filter5'
                    ]
                )
                ->build(),
            CustomAttributeFilterBuilder::init()
                ->boolFilter(false)
                ->customAttributeDefinitionId('custom_attribute_definition_id6')
                ->key('key6')
                ->numberFilter(
                    RangeBuilder::init()
                        ->max('max4')
                        ->min('min8')
                        ->build()
                )
                ->selectionUidsFilter(
                    [
                        'selection_uids_filter6',
                        'selection_uids_filter5'
                    ]
                )
                ->build()
        ]
    )
    ->enabledLocationIds(
        [
            'enabled_location_ids9',
            'enabled_location_ids0'
        ]
    )
    ->limit(16)
    ->build();
```

