
# Update Location Response

Response object returned by the [UpdateLocation](https://developer.squareup.com/reference/square_2021-08-18/locations-api/update-location) endpoint.

## Structure

`UpdateLocationResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Information on errors encountered during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `location` | [`?Location`](../../doc/models/location.md) | Optional | - | getLocation(): ?Location | setLocation(?Location location): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\UpdateLocationResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\LocationBuilder;
use SquareConnectAPILib\Models\Builders\AddressBuilder;
use SquareConnectAPILib\Models\Builders\BusinessHoursBuilder;
use SquareConnectAPILib\Models\Builders\BusinessHoursPeriodBuilder;
use SquareConnectAPILib\Models\Builders\CoordinatesBuilder;

$updateLocationResponse = UpdateLocationResponseBuilder::init()
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
            ->businessEmail('example@squareup.com')
            ->businessHours(
                BusinessHoursBuilder::init()
                    ->periods(
                        [
                            BusinessHoursPeriodBuilder::init()
                                ->dayOfWeek('MON')
                                ->endLocalTime('17:00')
                                ->startLocalTime('09:00')
                                ->build()
                        ]
                    )
                    ->build()
            )
            ->businessName('Business Name')
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
            ->description('Updated description')
            ->id('LOCATION_ID')
            ->instagramUsername('instagram')
            ->languageCode('en-US')
            ->mcc('1234')
            ->merchantId('MERCHANT_ID')
            ->name('Updated nickname')
            ->phoneNumber('5559211234')
            ->status('ACTIVE')
            ->timezone('America/New_York')
            ->twitterUsername('twitter')
            ->type('MOBILE')
            ->websiteUrl('examplewebsite.com')
            ->build()
    )
    ->build();
```

