
# Terminal Checkout Query Filter

## Structure

`TerminalCheckoutQueryFilter`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `createdAt` | [`?TimeRange`](../../doc/models/time-range.md) | Optional | Represents a generic time range. The start and end values are<br>represented in RFC 3339 format. Time ranges are customized to be<br>inclusive or exclusive based on the needs of a particular endpoint.<br>Refer to the relevant endpoint-specific documentation to determine<br>how time ranges are handled. | getCreatedAt(): ?TimeRange | setCreatedAt(?TimeRange createdAt): void |
| `deviceId` | `?string` | Optional | The `TerminalCheckout` objects associated with a specific device. If no device is specified, then all<br>`TerminalCheckout` objects for the merchant are displayed. | getDeviceId(): ?string | setDeviceId(?string deviceId): void |
| `status` | `?string` | Optional | Filtered results with the desired status of the `TerminalCheckout`.<br>Options: PENDING, IN_PROGRESS, CANCELED, COMPLETED | getStatus(): ?string | setStatus(?string status): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\TerminalCheckoutQueryFilterBuilder;
use SquareConnectAPILib\Models\Builders\TimeRangeBuilder;

$terminalCheckoutQueryFilter = TerminalCheckoutQueryFilterBuilder::init()
    ->createdAt(
        TimeRangeBuilder::init()
            ->endAt('end_at8')
            ->startAt('start_at4')
            ->build()
    )
    ->deviceId('device_id2')
    ->status('status8')
    ->build();
```

