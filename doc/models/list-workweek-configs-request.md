
# List Workweek Configs Request

A request for a set of `WorkweekConfig` objects.

## Structure

`ListWorkweekConfigsRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cursor` | `?string` | Optional | A pointer to the next page of `WorkweekConfig` results to fetch. | getCursor(): ?string | setCursor(?string cursor): void |
| `limit` | `?int` | Optional | The maximum number of `WorkweekConfigs` results to return per page. | getLimit(): ?int | setLimit(?int limit): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\ListWorkweekConfigsRequestBuilder;

$listWorkweekConfigsRequest = ListWorkweekConfigsRequestBuilder::init()
    ->cursor('cursor2')
    ->limit(178)
    ->build();
```

