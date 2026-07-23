
# Search Orders Source Filter

A filter based on order `source` information.

## Structure

`SearchOrdersSourceFilter`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `sourceNames` | `?(string[])` | Optional | Filters by the [Source](https://developer.squareup.com/reference/square_2021-08-18/objects/OrderSource) `name`. The filter returns any orders<br>with a `source.name` that matches any of the listed source names.<br><br>Max: 10 source names. | getSourceNames(): ?array | setSourceNames(?array sourceNames): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\SearchOrdersSourceFilterBuilder;

$searchOrdersSourceFilter = SearchOrdersSourceFilterBuilder::init()
    ->sourceNames(
        [
            'source_names0',
            'source_names1'
        ]
    )
    ->build();
```

