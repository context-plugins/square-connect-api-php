
# List Cash Drawer Shifts Request

## Structure

`ListCashDrawerShiftsRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `beginTime` | `?string` | Optional | The inclusive start time of the query on opened_at, in ISO 8601 format. | getBeginTime(): ?string | setBeginTime(?string beginTime): void |
| `cursor` | `?string` | Optional | Opaque cursor for fetching the next page of results. | getCursor(): ?string | setCursor(?string cursor): void |
| `endTime` | `?string` | Optional | The exclusive end date of the query on opened_at, in ISO 8601 format. | getEndTime(): ?string | setEndTime(?string endTime): void |
| `limit` | `?int` | Optional | Number of cash drawer shift events in a page of results (200 by<br>default, 1000 max).<br><br>**Constraints**: `<= 1000` | getLimit(): ?int | setLimit(?int limit): void |
| `locationId` | `string` | Required | The ID of the location to query for a list of cash drawer shifts.<br><br>**Constraints**: *Minimum Length*: `1` | getLocationId(): string | setLocationId(string locationId): void |
| `sortOrder` | `?string` | Optional | The order in which cash drawer shifts are listed in the response,<br>based on their opened_at field. Default value: ASC | getSortOrder(): ?string | setSortOrder(?string sortOrder): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\ListCashDrawerShiftsRequestBuilder;

$listCashDrawerShiftsRequest = ListCashDrawerShiftsRequestBuilder::init(
    'location_id2'
)
    ->beginTime('begin_time6')
    ->cursor('cursor2')
    ->endTime('end_time0')
    ->limit(242)
    ->sortOrder('sort_order8')
    ->build();
```

