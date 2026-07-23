
# Retrieve Location Response

Defines the fields that the
[RetrieveLocation](https://developer.squareup.com/reference/square_2021-08-18/locations-api/retrieve-location) endpoint returns
in a response.

## Structure

`RetrieveLocationResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Information on errors encountered during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `location` | [`?Location`](../../doc/models/location.md) | Optional | - | getLocation(): ?Location | setLocation(?Location location): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\RetrieveLocationResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\LocationBuilder;
use SquareConnectAPILib\Models\Builders\AddressBuilder;
use SquareConnectAPILib\Models\Builders\BusinessHoursBuilder;
use SquareConnectAPILib\Models\Builders\BusinessHoursPeriodBuilder;

$retrieveLocationResponse = RetrieveLocationResponseBuilder::init()
    ->errors(
        [
            ErrorBuilder::init(
                'category8',
                'code8'
            )
                ->detail('detail6')
                ->field('field4')
                ->build(),
            ErrorBuilder::init(
                'category8',
                'code8'
            )
                ->detail('detail6')
                ->field('field4')
                ->build(),
            ErrorBuilder::init(
                'category8',
                'code8'
            )
                ->detail('detail6')
                ->field('field4')
                ->build()
        ]
    )
    ->location(
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
            ->businessName('Jet Fuel Coffee')
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
            ->name('Jet Fuel Coffee - Grant Park')
            ->phoneNumber('+1 650-354-7217')
            ->status('ACTIVE')
            ->timezone('America/Los_Angeles')
            ->build()
    )
    ->build();
```

