
# Time Range

Represents a generic time range. The start and end values are
represented in RFC 3339 format. Time ranges are customized to be
inclusive or exclusive based on the needs of a particular endpoint.
Refer to the relevant endpoint-specific documentation to determine
how time ranges are handled.

## Structure

`TimeRange`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `endAt` | `?string` | Optional | A datetime value in RFC 3339 format indicating when the time range<br>ends. | getEndAt(): ?string | setEndAt(?string endAt): void |
| `startAt` | `?string` | Optional | A datetime value in RFC 3339 format indicating when the time range<br>starts. | getStartAt(): ?string | setStartAt(?string startAt): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\TimeRangeBuilder;

$timeRange = TimeRangeBuilder::init()
    ->endAt('end_at2')
    ->startAt('start_at0')
    ->build();
```

