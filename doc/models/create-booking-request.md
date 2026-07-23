
# Create Booking Request

## Structure

`CreateBookingRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `booking` | [`Booking`](../../doc/models/booking.md) | Required | Represents a booking as a time-bound service contract for a seller's staff member to provide a specified service<br>at a given location to a requesting customer in one or more appointment segments. | getBooking(): Booking | setBooking(Booking booking): void |
| `idempotencyKey` | `?string` | Optional | A unique key to make this request an idempotent operation.<br><br>**Constraints**: *Maximum Length*: `255` | getIdempotencyKey(): ?string | setIdempotencyKey(?string idempotencyKey): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CreateBookingRequestBuilder;
use SquareConnectAPILib\Models\Builders\BookingBuilder;
use SquareConnectAPILib\Models\Builders\AppointmentSegmentBuilder;

$createBookingRequest = CreateBookingRequestBuilder::init(
    BookingBuilder::init()
        ->appointmentSegments(
            [
                AppointmentSegmentBuilder::init(
                    60,
                    'RU3PBTZTK7DXZDQFCJHOK2MC',
                    1599775456731,
                    'TMXUrsBWWcHTt79t'
                )->build()
            ]
        )
        ->createdAt('created_at2')
        ->customerId('EX2QSVGTZN4K1E5QE1CBFNVQ8M')
        ->customerNote('customer_note6')
        ->id('id4')
        ->locationId('LEQHH0YY8B42M')
        ->startAt('2020-11-26T13:00:00Z')
        ->build()
)
    ->idempotencyKey('idempotency_key6')
    ->build();
```

