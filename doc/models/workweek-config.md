
# Workweek Config

Sets the day of the week and hour of the day that a business starts a
workweek. This is used to calculate overtime pay.

## Structure

`WorkweekConfig`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `createdAt` | `?string` | Optional | A read-only timestamp in RFC 3339 format; presented in UTC. | getCreatedAt(): ?string | setCreatedAt(?string createdAt): void |
| `id` | `?string` | Optional | The UUID for this object. | getId(): ?string | setId(?string id): void |
| `startOfDayLocalTime` | `string` | Required | The local time at which a business week ends. Represented as a<br>string in `HH:MM` format (`HH:MM:SS` is also accepted, but seconds are<br>truncated).<br><br>**Constraints**: *Minimum Length*: `1` | getStartOfDayLocalTime(): string | setStartOfDayLocalTime(string startOfDayLocalTime): void |
| `startOfWeek` | `string` | Required | The day of the week on which a business week ends for<br>compensation purposes. | getStartOfWeek(): string | setStartOfWeek(string startOfWeek): void |
| `updatedAt` | `?string` | Optional | A read-only timestamp in RFC 3339 format; presented in UTC. | getUpdatedAt(): ?string | setUpdatedAt(?string updatedAt): void |
| `version` | `?int` | Optional | Used for resolving concurrency issues. The request fails if the version<br>provided does not match the server version at the time of the request. If not provided,<br>Square executes a blind write; potentially overwriting data from another<br>write. | getVersion(): ?int | setVersion(?int version): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\WorkweekConfigBuilder;

$workweekConfig = WorkweekConfigBuilder::init(
    'start_of_day_local_time0',
    'start_of_week6'
)
    ->createdAt('created_at2')
    ->id('id4')
    ->updatedAt('updated_at0')
    ->version(84)
    ->build();
```

