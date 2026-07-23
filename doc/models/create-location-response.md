
# Create Location Response

Response object returned by the [CreateLocation](https://developer.squareup.com/reference/square_2021-08-18/locations-api/create-location) endpoint.

## Structure

`CreateLocationResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Information on errors encountered during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `location` | [`?Location`](../../doc/models/location.md) | Optional | - | getLocation(): ?Location | setLocation(?Location location): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CreateLocationResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\LocationBuilder;
use SquareConnectAPILib\Models\Builders\AddressBuilder;
use SquareConnectAPILib\Models\Builders\BusinessHoursBuilder;
use SquareConnectAPILib\Models\Builders\BusinessHoursPeriodBuilder;
use SquareConnectAPILib\Models\Builders\CoordinatesBuilder;

$createLocationResponse = CreateLocationResponseBuilder::init()
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
                    ->addressLine1('1234 Peachtree St. NE')
                    ->addressLine2('address_line_26')
                    ->addressLine3('address_line_32')
                    ->administrativeDistrictLevel1('GA')
                    ->administrativeDistrictLevel2('administrative_district_level_28')
                    ->locality('Atlanta')
                    ->postalCode('30309')
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
                    'CREDIT_CARD_PROCESSING'
                ]
            )
            ->coordinates(
                CoordinatesBuilder::init()
                    ->latitude(33.788567)
                    ->longitude(-84.466947)
                    ->build()
            )
            ->country('US')
            ->createdAt('2019-07-19T17:58:25Z')
            ->currency('USD')
            ->description('My new location.')
            ->id('LOCATION_ID')
            ->instagramUsername('instagram')
            ->languageCode('en-US')
            ->mcc('1234')
            ->merchantId('MERCHANT_ID')
            ->name('New location name')
            ->status('ACTIVE')
            ->twitterUsername('twitter')
            ->type('PHYSICAL')
            ->websiteUrl('examplewebsite.com')
            ->build()
    )
    ->build();
```

