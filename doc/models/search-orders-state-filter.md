
# Search Orders State Filter

Filter by the current order `state`.

## Structure

`SearchOrdersStateFilter`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `states` | `string[]` | Required | States to filter for. | getStates(): array | setStates(array states): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\SearchOrdersStateFilterBuilder;

$searchOrdersStateFilter = SearchOrdersStateFilterBuilder::init(
    [
        'states4',
        'states5',
        'states6'
    ]
)->build();
```

