
# Search Orders Sort

Sorting criteria for a `SearchOrders` request. Results can only be sorted
by a timestamp field.

## Structure

`SearchOrdersSort`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `sortField` | `string` | Required | The field to sort by.<br><br>__Important:__ When using a [DateTimeFilter](https://developer.squareup.com/reference/square_2021-08-18/objects/SearchOrdersFilter),<br>`sort_field` must match the timestamp field that the `DateTimeFilter` uses to<br>filter. For example, if you set your `sort_field` to `CLOSED_AT` and you use a<br>`DateTimeFilter`, your `DateTimeFilter` must filter for orders by their `CLOSED_AT` date.<br>If this field does not match the timestamp field in `DateTimeFilter`,<br>`SearchOrders` returns an error.<br><br>Default: `CREATED_AT`. | getSortField(): string | setSortField(string sortField): void |
| `sortOrder` | `?string` | Optional | The chronological order in which results are returned. Defaults to `DESC`. | getSortOrder(): ?string | setSortOrder(?string sortOrder): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\SearchOrdersSortBuilder;

$searchOrdersSort = SearchOrdersSortBuilder::init(
    'sort_field8'
)
    ->sortOrder('sort_order6')
    ->build();
```

