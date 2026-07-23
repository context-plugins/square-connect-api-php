
# List Locations Response

Defines the fields that are included in the response body of
a request to the __ListLocations__ endpoint.

One of `errors` or `locations` is present in a given response (never both).

## Structure

`ListLocationsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `locations` | [`?(Location[])`](../../doc/models/location.md) | Optional | The business locations. | getLocations(): ?array | setLocations(?array locations): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\ListLocationsResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\LocationBuilder;
use SquareConnectAPILib\Models\Builders\AddressBuilder;
use SquareConnectAPILib\Models\Builders\BusinessHoursBuilder;
use SquareConnectAPILib\Models\Builders\BusinessHoursPeriodBuilder;

$listLocationsResponse = ListLocationsResponseBuilder::init()
    ->errors(
        [
            ErrorBuilder::init(
                'category8',
                'code8'
            )
                ->detail('detail6')
                ->field('field4')
                ->build()
        ]
    )
    ->locations(
        [
            LocationBuilder::init()
                ->address(
                    AddressBuilder::init()
                        ->addressLine1('123 Main St')
                        ->addressLine2('address_line_26')
                        ->addressLine3('address_line_32')
                        ->administrativeDistrictLevel1('CA')
                        ->administrativeDistrictLevel2('administrative_district_level_28')
                        ->country('US')
                        ->locality('San Francisco')
                        ->postalCode('94114')
                        ->build()
                )
                ->businessEmail('business_email2')
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
                ->businessName('Pumbaa\'s business name')
                ->capabilities(
                    [
                        'CREDIT_CARD_PROCESSING'
                    ]
                )
                ->country('US')
                ->createdAt('2016-09-19T17:33:12Z')
                ->currency('USD')
                ->id('18YC4JDH91E1H')
                ->languageCode('en-US')
                ->merchantId('3MYCJG5GVYQ8Q')
                ->name('your location name')
                ->phoneNumber('+1 650-354-7217')
                ->status('ACTIVE')
                ->timezone('America/Los_Angeles')
                ->build()
        ]
    )
    ->build();
```

