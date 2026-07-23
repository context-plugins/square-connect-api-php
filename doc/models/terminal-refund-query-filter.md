
# Terminal Refund Query Filter

## Structure

`TerminalRefundQueryFilter`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `createdAt` | [`?TimeRange`](../../doc/models/time-range.md) | Optional | Represents a generic time range. The start and end values are<br>represented in RFC 3339 format. Time ranges are customized to be<br>inclusive or exclusive based on the needs of a particular endpoint.<br>Refer to the relevant endpoint-specific documentation to determine<br>how time ranges are handled. | getCreatedAt(): ?TimeRange | setCreatedAt(?TimeRange createdAt): void |
| `deviceId` | `?string` | Optional | `TerminalRefund` objects associated with a specific device. If no device is specified, then all<br>`TerminalRefund` objects for the signed-in account are displayed. | getDeviceId(): ?string | setDeviceId(?string deviceId): void |
| `status` | `?string` | Optional | Filtered results with the desired status of the `TerminalRefund`.<br>Options: `PENDING`, `IN_PROGRESS`, `CANCEL_REQUESTED`, `CANCELED`, or `COMPLETED`. | getStatus(): ?string | setStatus(?string status): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\TerminalRefundQueryFilterBuilder;
use SquareConnectAPILib\Models\Builders\TimeRangeBuilder;

$terminalRefundQueryFilter = TerminalRefundQueryFilterBuilder::init()
    ->createdAt(
        TimeRangeBuilder::init()
            ->endAt('end_at8')
            ->startAt('start_at4')
            ->build()
    )
    ->deviceId('device_id0')
    ->status('status6')
    ->build();
```

