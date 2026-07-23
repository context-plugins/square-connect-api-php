
# Update Booking Request

## Structure

`UpdateBookingRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `booking` | [`Booking`](../../doc/models/booking.md) | Required | Represents a booking as a time-bound service contract for a seller's staff member to provide a specified service<br>at a given location to a requesting customer in one or more appointment segments. | getBooking(): Booking | setBooking(Booking booking): void |
| `idempotencyKey` | `?string` | Optional | A unique key to make this request an idempotent operation.<br><br>**Constraints**: *Maximum Length*: `255` | getIdempotencyKey(): ?string | setIdempotencyKey(?string idempotencyKey): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\UpdateBookingRequestBuilder;
use SquareConnectAPILib\Models\Builders\BookingBuilder;
use SquareConnectAPILib\Models\Builders\AppointmentSegmentBuilder;

$updateBookingRequest = UpdateBookingRequestBuilder::init(
    BookingBuilder::init()
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
        ->customerNote('I would like to sit near the window please')
        ->id('id4')
        ->version(1)
        ->build()
)
    ->idempotencyKey('idempotency_key6')
    ->build();
```

