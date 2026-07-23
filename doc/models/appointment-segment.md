
# Appointment Segment

Defines an appointment segment of a booking.

## Structure

`AppointmentSegment`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `durationMinutes` | `int` | Required | The time span in minutes of an appointment segment.<br><br>**Constraints**: `>= 0`, `<= 1500` | getDurationMinutes(): int | setDurationMinutes(int durationMinutes): void |
| `serviceVariationId` | `string` | Required | The ID of the [CatalogItemVariation](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogItemVariation) object representing the service booked in this segment.<br><br>**Constraints**: *Minimum Length*: `1` | getServiceVariationId(): string | setServiceVariationId(string serviceVariationId): void |
| `serviceVariationVersion` | `int` | Required | The current version of the item variation representing the service booked in this segment. | getServiceVariationVersion(): int | setServiceVariationVersion(int serviceVariationVersion): void |
| `teamMemberId` | `string` | Required | The ID of the [TeamMember](https://developer.squareup.com/reference/square_2021-08-18/objects/TeamMember) object representing the team member booked in this segment.<br><br>**Constraints**: *Minimum Length*: `1` | getTeamMemberId(): string | setTeamMemberId(string teamMemberId): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\AppointmentSegmentBuilder;

$appointmentSegment = AppointmentSegmentBuilder::init(
    28,
    'service_variation_id6',
    196,
    'team_member_id8'
)->build();
```

