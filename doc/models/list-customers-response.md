
# List Customers Response

Defines the fields that are included in the response body of
a request to the `ListCustomers` endpoint.

Either `errors` or `customers` is present in a given response (never both).

## Structure

`ListCustomersResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cursor` | `?string` | Optional | A pagination cursor to retrieve the next set of results for the<br>original query. A cursor is only present if the request succeeded and additional results<br>are available.<br><br>For more information, see [Pagination](https://developer.squareup.com/docs/working-with-apis/pagination). | getCursor(): ?string | setCursor(?string cursor): void |
| `customers` | [`?(Customer[])`](../../doc/models/customer.md) | Optional | An array of `Customer` objects that match the provided query. | getCustomers(): ?array | setCustomers(?array customers): void |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\ListCustomersResponseBuilder;
use SquareConnectAPILib\Models\Builders\CustomerBuilder;
use SquareConnectAPILib\Models\Builders\AddressBuilder;
use SquareConnectAPILib\Models\Builders\CardBuilder;
use SquareConnectAPILib\Models\Builders\CustomerPreferencesBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;

$listCustomersResponse = ListCustomersResponseBuilder::init()
    ->cursor('cursor2')
    ->customers(
        [
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
                ->createdAt('2016-03-23T20:21:54.859Z')
                ->creationSource('THIRD_PARTY')
                ->emailAddress('Amelia.Earhart@example.com')
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
                ->referenceId('YOUR_REFERENCE_ID')
                ->segmentIds(
                    [
                        '1KB9JE5EGJXCW.REACHABLE'
                    ]
                )
                ->updatedAt('2016-03-23T20:21:55Z')
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
    ->build();
```

