
# List Cash Drawer Shift Events Request

## Structure

`ListCashDrawerShiftEventsRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cursor` | `?string` | Optional | Opaque cursor for fetching the next page of results. | getCursor(): ?string | setCursor(?string cursor): void |
| `limit` | `?int` | Optional | Number of resources to be returned in a page of results (200 by<br>default, 1000 max).<br><br>**Constraints**: `<= 1000` | getLimit(): ?int | setLimit(?int limit): void |
| `locationId` | `string` | Required | The ID of the location to list cash drawer shifts for.<br><br>**Constraints**: *Minimum Length*: `1` | getLocationId(): string | setLocationId(string locationId): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\ListCashDrawerShiftEventsRequestBuilder;

$listCashDrawerShiftEventsRequest = ListCashDrawerShiftEventsRequestBuilder::init(
    'location_id4'
)
    ->cursor('cursor6')
    ->limit(56)
    ->build();
```

