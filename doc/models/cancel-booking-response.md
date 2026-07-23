
# Cancel Booking Response

## Structure

`CancelBookingResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `booking` | [`?Booking`](../../doc/models/booking.md) | Optional | Represents a booking as a time-bound service contract for a seller's staff member to provide a specified service<br>at a given location to a requesting customer in one or more appointment segments. | getBooking(): ?Booking | setBooking(?Booking booking): void |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CancelBookingResponseBuilder;
use SquareConnectAPILib\Models\Builders\BookingBuilder;
use SquareConnectAPILib\Models\Builders\AppointmentSegmentBuilder;

$cancelBookingResponse = CancelBookingResponseBuilder::init()
    ->booking(
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
            ->createdAt('2020-10-28T15:47:41Z')
            ->customerId('EX2QSVGTZN4K1E5QE1CBFNVQ8M')
            ->customerNote('')
            ->id('zkras0xv0xwswx')
            ->locationId('LEQHH0YY8B42M')
            ->sellerNote('')
            ->startAt('2020-11-26T13:00:00Z')
            ->status('CANCELLED_BY_CUSTOMER')
            ->updatedAt('2020-10-28T15:49:25Z')
            ->version(1)
            ->build()
    )
    ->errors(
        []
    )
    ->build();
```

