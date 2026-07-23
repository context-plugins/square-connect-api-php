
# Search Customers Response

Defines the fields that are included in the response body of
a request to the `SearchCustomers` endpoint.

Either `errors` or `customers` is present in a given response (never both).

## Structure

`SearchCustomersResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cursor` | `?string` | Optional | A pagination cursor that can be used during subsequent calls<br>to `SearchCustomers` to retrieve the next set of results associated<br>with the original query. Pagination cursors are only present when<br>a request succeeds and additional results are available.<br><br>For more information, see [Pagination](https://developer.squareup.com/docs/working-with-apis/pagination). | getCursor(): ?string | setCursor(?string cursor): void |
| `customers` | [`?(Customer[])`](../../doc/models/customer.md) | Optional | An array of `Customer` objects that match a query. | getCustomers(): ?array | setCustomers(?array customers): void |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\SearchCustomersResponseBuilder;
use SquareConnectAPILib\Models\Builders\CustomerBuilder;
use SquareConnectAPILib\Models\Builders\AddressBuilder;
use SquareConnectAPILib\Models\Builders\CardBuilder;
use SquareConnectAPILib\Models\Builders\CustomerPreferencesBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;

$searchCustomersResponse = SearchCustomersResponseBuilder::init()
    ->cursor('9dpS093Uy12AzeE')
    ->customers(
        [
            CustomerBuilder::init()
                ->address(
                    AddressBuilder::init()
                        ->addressLine1('505 Electric Ave')
                        ->addressLine2('Suite 600')
                        ->addressLine3('address_line_32')
                        ->administrativeDistrictLevel1('NY')
                        ->administrativeDistrictLevel2('administrative_district_level_28')
                        ->country('US')
                        ->locality('New York')
                        ->postalCode('10003')
                        ->build()
                )
                ->birthday('birthday2')
                ->cards(
                    [
                        CardBuilder::init()
                            ->billingAddress(
                                AddressBuilder::init()
                                    ->addressLine1('address_line_12')
                                    ->addressLine2('address_line_28')
                                    ->addressLine3('address_line_34')
                                    ->administrativeDistrictLevel1('administrative_district_level_12')
                                    ->administrativeDistrictLevel2('administrative_district_level_26')
                                    ->build()
                            )
                            ->bin('bin8')
                            ->cardBrand('card_brand8')
                            ->cardType('card_type6')
                            ->cardholderName('cardholder_name6')
                            ->build(),
                        CardBuilder::init()
                            ->billingAddress(
                                AddressBuilder::init()
                                    ->addressLine1('address_line_12')
                                    ->addressLine2('address_line_28')
                                    ->addressLine3('address_line_34')
                                    ->administrativeDistrictLevel1('administrative_district_level_12')
                                    ->administrativeDistrictLevel2('administrative_district_level_26')
                                    ->build()
                            )
                            ->bin('bin8')
                            ->cardBrand('card_brand8')
                            ->cardType('card_type6')
                            ->cardholderName('cardholder_name6')
                            ->build()
                    ]
                )
                ->companyName('company_name8')
                ->createdAt('2018-01-23T20:21:54.859Z')
                ->creationSource('DIRECTORY')
                ->emailAddress('james.bond@example.com')
                ->familyName('Bond')
                ->givenName('James')
                ->groupIds(
                    [
                        '545AXB44B4XXWMVQ4W8SBT3HHF'
                    ]
                )
                ->id('JDKYHBWT1D4F8MFH63DBMEN8Y4')
                ->phoneNumber('1-212-555-4250')
                ->preferences(
                    CustomerPreferencesBuilder::init()
                        ->emailUnsubscribed(false)
                        ->build()
                )
                ->referenceId('YOUR_REFERENCE_ID_2')
                ->segmentIds(
                    [
                        '1KB9JE5EGJXCW.REACHABLE'
                    ]
                )
                ->updatedAt('2020-04-20T10:02:43.083Z')
                ->version(7)
                ->build(),
            CustomerBuilder::init()
                ->address(
                    AddressBuilder::init()
                        ->addressLine1('500 Electric Ave')
                        ->addressLine2('Suite 600')
                        ->addressLine3('address_line_32')
                        ->administrativeDistrictLevel1('NY')
                        ->administrativeDistrictLevel2('administrative_district_level_28')
                        ->country('US')
                        ->locality('New York')
                        ->postalCode('10003')
                        ->build()
                )
                ->birthday('birthday2')
                ->cards(
                    [
                        CardBuilder::init()
                            ->billingAddress(
                                AddressBuilder::init()
                                    ->addressLine1('address_line_12')
                                    ->addressLine2('address_line_28')
                                    ->addressLine3('address_line_34')
                                    ->administrativeDistrictLevel1('administrative_district_level_12')
                                    ->administrativeDistrictLevel2('administrative_district_level_26')
                                    ->build()
                            )
                            ->bin('bin8')
                            ->cardBrand('card_brand8')
                            ->cardType('card_type6')
                            ->cardholderName('cardholder_name6')
                            ->build(),
                        CardBuilder::init()
                            ->billingAddress(
                                AddressBuilder::init()
                                    ->addressLine1('address_line_12')
                                    ->addressLine2('address_line_28')
                                    ->addressLine3('address_line_34')
                                    ->administrativeDistrictLevel1('administrative_district_level_12')
                                    ->administrativeDistrictLevel2('administrative_district_level_26')
                                    ->build()
                            )
                            ->bin('bin8')
                            ->cardBrand('card_brand8')
                            ->cardType('card_type6')
                            ->cardholderName('cardholder_name6')
                            ->build()
                    ]
                )
                ->companyName('company_name8')
                ->createdAt('2018-01-30T14:10:54.859Z')
                ->creationSource('THIRD_PARTY')
                ->emailAddress('amelia.earhart@example.com')
                ->familyName('Earhart')
                ->givenName('Amelia')
                ->groupIds(
                    [
                        '545AXB44B4XXWMVQ4W8SBT3HHF'
                    ]
                )
                ->id('JDKYHBWT1D4F8MFH63DBMEN8Y4')
                ->note('a customer')
                ->phoneNumber('1-212-555-4240')
                ->preferences(
                    CustomerPreferencesBuilder::init()
                        ->emailUnsubscribed(false)
                        ->build()
                )
                ->referenceId('YOUR_REFERENCE_ID_1')
                ->segmentIds(
                    [
                        '1KB9JE5EGJXCW.REACHABLE'
                    ]
                )
                ->updatedAt('2018-03-08T18:25:21.342Z')
                ->version(1)
                ->build()
        ]
    )
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
    ->build();
```

