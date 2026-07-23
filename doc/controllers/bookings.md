# Bookings

```php
$bookingsController = $client->getBookingsController();
```

## Class Name

`BookingsController`

## Methods

* [Create Booking](../../doc/controllers/bookings.md#create-booking)
* [Search Availability](../../doc/controllers/bookings.md#search-availability)
* [Retrieve Business Booking Profile](../../doc/controllers/bookings.md#retrieve-business-booking-profile)
* [List Team Member Booking Profiles](../../doc/controllers/bookings.md#list-team-member-booking-profiles)
* [Retrieve Team Member Booking Profile](../../doc/controllers/bookings.md#retrieve-team-member-booking-profile)
* [Retrieve Booking](../../doc/controllers/bookings.md#retrieve-booking)
* [Update Booking](../../doc/controllers/bookings.md#update-booking)
* [Cancel Booking](../../doc/controllers/bookings.md#cancel-booking)


# Create Booking

Creates a booking.

```php
function createBooking(CreateBookingRequest $body): CreateBookingResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`CreateBookingRequest`](../../doc/models/create-booking-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`APPOINTMENTS_WRITE`

## Response Type

**200**: Success

[`CreateBookingResponse`](../../doc/models/create-booking-response.md)

## Example Usage

```php
$body = CreateBookingRequestBuilder::init(
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
        ->customerId('EX2QSVGTZN4K1E5QE1CBFNVQ8M')
        ->locationId('LEQHH0YY8B42M')
        ->startAt('2020-11-26T13:00:00Z')
        ->build()
)->build();

$bookingsController = $client->getBookingsController();

try {
    $result = $bookingsController->createBooking($body);
    echo 'CreateBookingResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Search Availability

Searches for availabilities for booking.

```php
function searchAvailability(SearchAvailabilityRequest $body): SearchAvailabilityResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`SearchAvailabilityRequest`](../../doc/models/search-availability-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`APPOINTMENTS_READ`

## Response Type

**200**: Success

[`SearchAvailabilityResponse`](../../doc/models/search-availability-response.md)

## Example Usage

```php
$body = SearchAvailabilityRequestBuilder::init(
    SearchAvailabilityQueryBuilder::init(
        SearchAvailabilityFilterBuilder::init(
            TimeRangeBuilder::init()
                ->endAt('2020-11-27T13:00:00Z')
                ->startAt('2020-11-26T13:00:00Z')
                ->build()
        )
            ->locationId('LEQHH0YY8B42M')
            ->segmentFilters(
                [
                    SegmentFilterBuilder::init(
                        'RU3PBTZTK7DXZDQFCJHOK2MC'
                    )
                        ->teamMemberIdFilter(
                            FilterValueBuilder::init()
                                ->any(
                                    [
                                        'TMXUrsBWWcHTt79t',
                                        'TMaJcbiRqPIGZuS9'
                                    ]
                                )
                                ->build()
                        )
                        ->build()
                ]
            )
            ->build()
    )->build()
)->build();

$bookingsController = $client->getBookingsController();

try {
    $result = $bookingsController->searchAvailability($body);
    echo 'SearchAvailabilityResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Retrieve Business Booking Profile

Retrieves a seller's booking profile.

```php
function retrieveBusinessBookingProfile(): RetrieveBusinessBookingProfileResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Requires scope

### oauth2

`APPOINTMENTS_BUSINESS_SETTINGS_READ`

## Response Type

**200**: Success

[`RetrieveBusinessBookingProfileResponse`](../../doc/models/retrieve-business-booking-profile-response.md)

## Example Usage

```php
$bookingsController = $client->getBookingsController();

try {
    $result = $bookingsController->retrieveBusinessBookingProfile();
    echo 'RetrieveBusinessBookingProfileResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# List Team Member Booking Profiles

Lists booking profiles for team members.

```php
function listTeamMemberBookingProfiles(
    ?bool $bookableOnly = null,
    ?int $limit = null,
    ?string $cursor = null,
    ?string $locationId = null
): ListTeamMemberBookingProfilesResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `bookableOnly` | `?bool` | Query, Optional | Indicates whether to include only bookable team members in the returned result (`true`) or not (`false`). |
| `limit` | `?int` | Query, Optional | The maximum number of results to return. |
| `cursor` | `?string` | Query, Optional | The cursor for paginating through the results. |
| `locationId` | `?string` | Query, Optional | Indicates whether to include only team members enabled at the given location in the returned result. |

## Requires scope

### oauth2

`APPOINTMENTS_BUSINESS_SETTINGS_READ`

## Response Type

**200**: Success

[`ListTeamMemberBookingProfilesResponse`](../../doc/models/list-team-member-booking-profiles-response.md)

## Example Usage

```php
$bookingsController = $client->getBookingsController();

try {
    $result = $bookingsController->listTeamMemberBookingProfiles();
    echo 'ListTeamMemberBookingProfilesResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Retrieve Team Member Booking Profile

Retrieves a team member's booking profile.

```php
function retrieveTeamMemberBookingProfile(string $teamMemberId): RetrieveTeamMemberBookingProfileResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `teamMemberId` | `string` | Template, Required | The ID of the team member to retrieve. |

## Requires scope

### oauth2

`APPOINTMENTS_BUSINESS_SETTINGS_READ`

## Response Type

**200**: Success

[`RetrieveTeamMemberBookingProfileResponse`](../../doc/models/retrieve-team-member-booking-profile-response.md)

## Example Usage

```php
$teamMemberId = 'team_member_id0';

$bookingsController = $client->getBookingsController();

try {
    $result = $bookingsController->retrieveTeamMemberBookingProfile($teamMemberId);
    echo 'RetrieveTeamMemberBookingProfileResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Retrieve Booking

Retrieves a booking.

```php
function retrieveBooking(string $bookingId): RetrieveBookingResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `bookingId` | `string` | Template, Required | The ID of the [Booking](https://developer.squareup.com/reference/square_2021-08-18/objects/Booking) object representing the to-be-retrieved booking. |

## Requires scope

### oauth2

`APPOINTMENTS_READ`

## Response Type

**200**: Success

[`RetrieveBookingResponse`](../../doc/models/retrieve-booking-response.md)

## Example Usage

```php
$bookingId = 'booking_id4';

$bookingsController = $client->getBookingsController();

try {
    $result = $bookingsController->retrieveBooking($bookingId);
    echo 'RetrieveBookingResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Update Booking

Updates a booking.

```php
function updateBooking(string $bookingId, UpdateBookingRequest $body): UpdateBookingResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `bookingId` | `string` | Template, Required | The ID of the [Booking](https://developer.squareup.com/reference/square_2021-08-18/objects/Booking) object representing the to-be-updated booking. |
| `body` | [`UpdateBookingRequest`](../../doc/models/update-booking-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`APPOINTMENTS_WRITE`

## Response Type

**200**: Success

[`UpdateBookingResponse`](../../doc/models/update-booking-response.md)

## Example Usage

```php
$bookingId = 'booking_id4';

$body = UpdateBookingRequestBuilder::init(
    BookingBuilder::init()
        ->customerNote('I would like to sit near the window please')
        ->version(1)
        ->build()
)->build();

$bookingsController = $client->getBookingsController();

try {
    $result = $bookingsController->updateBooking(
        $bookingId,
        $body
    );
    echo 'UpdateBookingResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Cancel Booking

Cancels an existing booking.

```php
function cancelBooking(string $bookingId, CancelBookingRequest $body): CancelBookingResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `bookingId` | `string` | Template, Required | The ID of the [Booking](https://developer.squareup.com/reference/square_2021-08-18/objects/Booking) object representing the to-be-cancelled booking. |
| `body` | [`CancelBookingRequest`](../../doc/models/cancel-booking-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`APPOINTMENTS_WRITE`

## Response Type

**200**: Success

[`CancelBookingResponse`](../../doc/models/cancel-booking-response.md)

## Example Usage

```php
$bookingId = 'booking_id4';

$body = CancelBookingRequestBuilder::init()
    ->bookingVersion(1)
    ->build();

$bookingsController = $client->getBookingsController();

try {
    $result = $bookingsController->cancelBooking(
        $bookingId,
        $body
    );
    echo 'CancelBookingResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

