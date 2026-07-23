
# Custom Attribute Filter

Supported custom attribute query expressions for calling the
[SearchCatalogItems](https://developer.squareup.com/reference/square_2021-08-18/catalog-api/search-catalog-items)
endpoint to search for items or item variations.

## Structure

`CustomAttributeFilter`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `boolFilter` | `?bool` | Optional | A query expression to filter items or item variations by matching their custom attributes'<br>`boolean_value` property values<br>against the specified Boolean expression. | getBoolFilter(): ?bool | setBoolFilter(?bool boolFilter): void |
| `customAttributeDefinitionId` | `?string` | Optional | A query expression to filter items or item variations by matching their custom attributes'<br>`custom_attribute_definition_id`<br>property value against the the specified id. | getCustomAttributeDefinitionId(): ?string | setCustomAttributeDefinitionId(?string customAttributeDefinitionId): void |
| `key` | `?string` | Optional | A query expression to filter items or item variations by matching their custom attributes'<br>`key` property value against<br>the specified key. | getKey(): ?string | setKey(?string key): void |
| `numberFilter` | [`?Range`](../../doc/models/range.md) | Optional | The range of a number value between the specified lower and upper bounds. | getNumberFilter(): ?Range | setNumberFilter(?Range numberFilter): void |
| `selectionUidsFilter` | `?(string[])` | Optional | A query expression to filter items or item variations by matching  their custom attributes'<br>`selection_uid_values`<br>values against the specified selection uids. | getSelectionUidsFilter(): ?array | setSelectionUidsFilter(?array selectionUidsFilter): void |
| `stringFilter` | `?string` | Optional | A query expression to filter items or item variations by matching their custom attributes'<br>`string_value`  property value<br>against the specified text. | getStringFilter(): ?string | setStringFilter(?string stringFilter): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CustomAttributeFilterBuilder;
use SquareConnectAPILib\Models\Builders\RangeBuilder;

$customAttributeFilter = CustomAttributeFilterBuilder::init()
    ->boolFilter(false)
    ->customAttributeDefinitionId('custom_attribute_definition_id2')
    ->key('key0')
    ->numberFilter(
        RangeBuilder::init()
            ->max('max4')
            ->min('min8')
            ->build()
    )
    ->selectionUidsFilter(
        [
            'selection_uids_filter4',
            'selection_uids_filter5',
            'selection_uids_filter6'
        ]
    )
    ->build();
```

