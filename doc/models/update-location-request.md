
# Update Location Request

Request object for the [UpdateLocation](https://developer.squareup.com/reference/square_2021-08-18/locations-api/update-location) endpoint.

## Structure

`UpdateLocationRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `location` | [`?Location`](../../doc/models/location.md) | Optional | - | getLocation(): ?Location | setLocation(?Location location): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\UpdateLocationRequestBuilder;
use SquareConnectAPILib\Models\Builders\LocationBuilder;
use SquareConnectAPILib\Models\Builders\AddressBuilder;
use SquareConnectAPILib\Models\Builders\BusinessHoursBuilder;
use SquareConnectAPILib\Models\Builders\BusinessHoursPeriodBuilder;

$updateLocationRequest = UpdateLocationRequestBuilder::init()
    ->location(
        LocationBuilder::init()
            ->address(
                AddressBuilder::init()
                    ->addressLine1('address_line_16')
                    ->addressLine2('address_line_26')
                    ->addressLine3('address_line_32')
                    ->administrativeDistrictLevel1('administrative_district_level_10')
                    ->administrativeDistrictLevel2('administrative_district_level_28')
                    ->build()
            )
            ->businessEmail('business_email8')
            ->businessHours(
                BusinessHoursBuilder::init()
                    ->periods(
                        [
                            BusinessHoursPeriodBuilder::init()
                                ->dayOfWeek('day_of_week2')
                                ->endLocalTime('end_local_time6')
                                ->startLocalTime('start_local_time4')
                                ->build(),
                            BusinessHoursPeriodBuilder::init()
                                ->dayOfWeek('day_of_week2')
                                ->endLocalTime('end_local_time6')
                                ->startLocalTime('start_local_time4')
                                ->build(),
                            BusinessHoursPeriodBuilder::init()
                                ->dayOfWeek('day_of_week2')
                                ->endLocalTime('end_local_time6')
                                ->startLocalTime('start_local_time4')
                                ->build()
                        ]
                    )
                    ->build()
            )
            ->businessName('business_name8')
            ->capabilities(
                [
                    'capabilities3'
                ]
            )
            ->build()
    )
    ->build();
```

