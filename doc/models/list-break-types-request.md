
# List Break Types Request

A request for a filtered set of `BreakType` objects.

## Structure

`ListBreakTypesRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cursor` | `?string` | Optional | A pointer to the next page of `BreakType` results to fetch. | getCursor(): ?string | setCursor(?string cursor): void |
| `limit` | `?int` | Optional | The maximum number of `BreakType` results to return per page. The number can range between 1<br>and 200. The default is 200.<br><br>**Constraints**: `>= 1`, `<= 200` | getLimit(): ?int | setLimit(?int limit): void |
| `locationId` | `?string` | Optional | Filter the returned `BreakType` results to only those that are associated with the<br>specified location. | getLocationId(): ?string | setLocationId(?string locationId): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\ListBreakTypesRequestBuilder;

$listBreakTypesRequest = ListBreakTypesRequestBuilder::init()
    ->cursor('cursor2')
    ->limit(200)
    ->locationId('location_id8')
    ->build();
```

