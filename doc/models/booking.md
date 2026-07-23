
# Booking

Represents a booking as a time-bound service contract for a seller's staff member to provide a specified service
at a given location to a requesting customer in one or more appointment segments.

## Structure

`Booking`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `appointmentSegments` | [`?(AppointmentSegment[])`](../../doc/models/appointment-segment.md) | Optional | A list of appointment segments for this booking. | getAppointmentSegments(): ?array | setAppointmentSegments(?array appointmentSegments): void |
| `createdAt` | `?string` | Optional | The timestamp specifying the creation time of this booking, in RFC 3339 format. | getCreatedAt(): ?string | setCreatedAt(?string createdAt): void |
| `customerId` | `?string` | Optional | The ID of the [Customer](https://developer.squareup.com/reference/square_2021-08-18/objects/Customer) object representing the customer attending this booking | getCustomerId(): ?string | setCustomerId(?string customerId): void |
| `customerNote` | `?string` | Optional | The free-text field for the customer to supply notes about the booking. For example, the note can be preferences that cannot be expressed by supported attributes of a relevant [CatalogObject](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogObject) instance.<br><br>**Constraints**: *Maximum Length*: `4096` | getCustomerNote(): ?string | setCustomerNote(?string customerNote): void |
| `id` | `?string` | Optional | A unique ID of this object representing a booking. | getId(): ?string | setId(?string id): void |
| `locationId` | `?string` | Optional | The ID of the [Location](https://developer.squareup.com/reference/square_2021-08-18/objects/Location) object representing the location where the booked service is provided. | getLocationId(): ?string | setLocationId(?string locationId): void |
| `sellerNote` | `?string` | Optional | The free-text field for the seller to supply notes about the booking. For example, the note can be preferences that cannot be expressed by supported attributes of a specific [CatalogObject](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogObject) instance.<br>This field should not be visible to customers.<br><br>**Constraints**: *Maximum Length*: `4096` | getSellerNote(): ?string | setSellerNote(?string sellerNote): void |
| `startAt` | `?string` | Optional | The timestamp specifying the starting time of this booking, in RFC 3339 format. | getStartAt(): ?string | setStartAt(?string startAt): void |
| `status` | `?string` | Optional | The status of the booking, describing where the booking stands with respect to the booking state machine. | getStatus(): ?string | setStatus(?string status): void |
| `updatedAt` | `?string` | Optional | The timestamp specifying the most recent update time of this booking, in RFC 3339 format. | getUpdatedAt(): ?string | setUpdatedAt(?string updatedAt): void |
| `version` | `?int` | Optional | The revision number for the booking used for optimistic concurrency.<br><br>**Constraints**: `>= 0` | getVersion(): ?int | setVersion(?int version): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\BookingBuilder;
use SquareConnectAPILib\Models\Builders\AppointmentSegmentBuilder;

$booking = BookingBuilder::init()
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
            )->build()
        ]
    )
    ->createdAt('created_at2')
    ->customerId('customer_id2')
    ->customerNote('customer_note6')
    ->id('id4')
    ->build();
```

