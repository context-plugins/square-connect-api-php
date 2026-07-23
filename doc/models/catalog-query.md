
# Catalog Query

A query composed of one or more different types of filters to narrow the scope of targeted objects when calling the `SearchCatalogObjects` endpoint.

Although a query can have multiple filters, only certain query types can be combined per call to [SearchCatalogObjects](https://developer.squareup.com/reference/square_2021-08-18/catalog-api/search-catalog-objects).
Any combination of the following types may be used together:

- [exact_query](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogQueryExact)
- [prefix_query](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogQueryPrefix)
- [range_query](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogQueryRange)
- [sorted_attribute_query](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogQuerySortedAttribute)
- [text_query](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogQueryText)
  All other query types cannot be combined with any others.

When a query filter is based on an attribute, the attribute must be searchable.
Searchable attributes are listed as follows, along their parent types that can be searched for with applicable query filters.

* Searchable attribute and objects queryable by searchable attributes **

- `name`:  `CatalogItem`, `CatalogItemVariation`, `CatalogCategory`, `CatalogTax`, `CatalogDiscount`, `CatalogModifier`, 'CatalogModifierList`, `CatalogItemOption`, `CatalogItemOptionValue`
- `description`: `CatalogItem`, `CatalogItemOptionValue`
- `abbreviation`: `CatalogItem`
- `upc`: `CatalogItemVariation`
- `sku`: `CatalogItemVariation`
- `caption`: `CatalogImage`
- `display_name`: `CatalogItemOption`

For example, to search for [CatalogItem](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogItem) objects by searchable attributes, you can use
the `"name"`, `"description"`, or `"abbreviation"` attribute in an applicable query filter.

## Structure

`CatalogQuery`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `exactQuery` | [`?CatalogQueryExact`](../../doc/models/catalog-query-exact.md) | Optional | The query filter to return the search result by exact match of the specified attribute name and value. | getExactQuery(): ?CatalogQueryExact | setExactQuery(?CatalogQueryExact exactQuery): void |
| `itemVariationsForItemOptionValuesQuery` | [`?CatalogQueryItemVariationsForItemOptionValues`](../../doc/models/catalog-query-item-variations-for-item-option-values.md) | Optional | The query filter to return the item variations containing the specified item option value IDs. | getItemVariationsForItemOptionValuesQuery(): ?CatalogQueryItemVariationsForItemOptionValues | setItemVariationsForItemOptionValuesQuery(?CatalogQueryItemVariationsForItemOptionValues itemVariationsForItemOptionValuesQuery): void |
| `itemsForItemOptionsQuery` | [`?CatalogQueryItemsForItemOptions`](../../doc/models/catalog-query-items-for-item-options.md) | Optional | The query filter to return the items containing the specified item option IDs. | getItemsForItemOptionsQuery(): ?CatalogQueryItemsForItemOptions | setItemsForItemOptionsQuery(?CatalogQueryItemsForItemOptions itemsForItemOptionsQuery): void |
| `itemsForModifierListQuery` | [`?CatalogQueryItemsForModifierList`](../../doc/models/catalog-query-items-for-modifier-list.md) | Optional | The query filter to return the items containing the specified modifier list IDs. | getItemsForModifierListQuery(): ?CatalogQueryItemsForModifierList | setItemsForModifierListQuery(?CatalogQueryItemsForModifierList itemsForModifierListQuery): void |
| `itemsForTaxQuery` | [`?CatalogQueryItemsForTax`](../../doc/models/catalog-query-items-for-tax.md) | Optional | The query filter to return the items containing the specified tax IDs. | getItemsForTaxQuery(): ?CatalogQueryItemsForTax | setItemsForTaxQuery(?CatalogQueryItemsForTax itemsForTaxQuery): void |
| `prefixQuery` | [`?CatalogQueryPrefix`](../../doc/models/catalog-query-prefix.md) | Optional | The query filter to return the search result whose named attribute values are prefixed by the specified attribute value. | getPrefixQuery(): ?CatalogQueryPrefix | setPrefixQuery(?CatalogQueryPrefix prefixQuery): void |
| `rangeQuery` | [`?CatalogQueryRange`](../../doc/models/catalog-query-range.md) | Optional | The query filter to return the search result whose named attribute values fall between the specified range. | getRangeQuery(): ?CatalogQueryRange | setRangeQuery(?CatalogQueryRange rangeQuery): void |
| `setQuery` | [`?CatalogQuerySet`](../../doc/models/catalog-query-set.md) | Optional | The query filter to return the search result(s) by exact match of the specified `attribute_name` and any of<br>the `attribute_values`. | getSetQuery(): ?CatalogQuerySet | setSetQuery(?CatalogQuerySet setQuery): void |
| `sortedAttributeQuery` | [`?CatalogQuerySortedAttribute`](../../doc/models/catalog-query-sorted-attribute.md) | Optional | The query expression to specify the key to sort search results. | getSortedAttributeQuery(): ?CatalogQuerySortedAttribute | setSortedAttributeQuery(?CatalogQuerySortedAttribute sortedAttributeQuery): void |
| `textQuery` | [`?CatalogQueryText`](../../doc/models/catalog-query-text.md) | Optional | The query filter to return the search result whose searchable attribute values contain all of the specified keywords or tokens, independent of the token order or case. | getTextQuery(): ?CatalogQueryText | setTextQuery(?CatalogQueryText textQuery): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CatalogQueryBuilder;
use SquareConnectAPILib\Models\Builders\CatalogQueryExactBuilder;
use SquareConnectAPILib\Models\Builders\CatalogQueryItemVariationsForItemOptionValuesBuilder;
use SquareConnectAPILib\Models\Builders\CatalogQueryItemsForItemOptionsBuilder;
use SquareConnectAPILib\Models\Builders\CatalogQueryItemsForModifierListBuilder;
use SquareConnectAPILib\Models\Builders\CatalogQueryItemsForTaxBuilder;

$catalogQuery = CatalogQueryBuilder::init()
    ->exactQuery(
        CatalogQueryExactBuilder::init(
            'attribute_name4',
            'attribute_value6'
        )->build()
    )
    ->itemVariationsForItemOptionValuesQuery(
        CatalogQueryItemVariationsForItemOptionValuesBuilder::init()
            ->itemOptionValueIds(
                [
                    'item_option_value_ids8',
                    'item_option_value_ids9',
                    'item_option_value_ids0'
                ]
            )
            ->build()
    )
    ->itemsForItemOptionsQuery(
        CatalogQueryItemsForItemOptionsBuilder::init()
            ->itemOptionIds(
                [
                    'item_option_ids9',
                    'item_option_ids0'
                ]
            )
            ->build()
    )
    ->itemsForModifierListQuery(
        CatalogQueryItemsForModifierListBuilder::init(
            [
                'modifier_list_ids6',
                'modifier_list_ids7',
                'modifier_list_ids8'
            ]
        )->build()
    )
    ->itemsForTaxQuery(
        CatalogQueryItemsForTaxBuilder::init(
            [
                'tax_ids3'
            ]
        )->build()
    )->build();
```

