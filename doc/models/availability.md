
# Availability

Describes a slot available for booking, encapsulating appointment segments, the location and starting time.

## Structure

`Availability`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `appointmentSegments` | [`?(AppointmentSegment[])`](../../doc/models/appointment-segment.md) | Optional | The list of appointment segments available for booking | getAppointmentSegments(): ?array | setAppointmentSegments(?array appointmentSegments): void |
| `locationId` | `?string` | Optional | The ID of the location available for booking. | getLocationId(): ?string | setLocationId(?string locationId): void |
| `startAt` | `?string` | Optional | The RFC 3339 timestamp specifying the beginning time of the slot available for booking. | getStartAt(): ?string | setStartAt(?string startAt): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\AvailabilityBuilder;
use SquareConnectAPILib\Models\Builders\AppointmentSegmentBuilder;

$availability = AvailabilityBuilder::init()
    ->appointmentSegments(
        [
            AppointmentSegmentBuilder::init(
                136,
                'service_variation_id4',
                48,
                'team_member_id0'
            )->build(),
            AppointmentSegmentBuilder::init(
                136,
                'service_variation_id4',
                48,
                'team_member_id0'
            )->build(),
            AppointmentSegmentBuilder::init(
                136,
                'service_variation_id4',
                48,
                'team_member_id0'
            )->build()
        ]
    )
    ->locationId('location_id4')
    ->startAt('start_at2')
    ->build();
```

