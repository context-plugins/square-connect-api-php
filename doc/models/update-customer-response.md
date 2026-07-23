
# Update Customer Response

Defines the fields that are included in the response body of
a request to the `UpdateCustomer` endpoint.

Either `errors` or `customer` is present in a given response (never both).

## Structure

`UpdateCustomerResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `customer` | [`?Customer`](../../doc/models/customer.md) | Optional | Represents a Square customer profile in the Customer Directory of a Square seller. | getCustomer(): ?Customer | setCustomer(?Customer customer): void |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\UpdateCustomerResponseBuilder;
use SquareConnectAPILib\Models\Builders\CustomerBuilder;
use SquareConnectAPILib\Models\Builders\AddressBuilder;
use SquareConnectAPILib\Models\Builders\CardBuilder;
use SquareConnectAPILib\Models\Builders\CustomerPreferencesBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;

$updateCustomerResponse = UpdateCustomerResponseBuilder::init()
    ->customer(
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
            ->birthday('birthday0')
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
                        ->build()
                ]
            )
            ->companyName('company_name6')
            ->createdAt('2016-03-23T20:21:54.859Z')
            ->creationSource('THIRD_PARTY')
            ->emailAddress('New.Amelia.Earhart@example.com')
            ->familyName('Earhart')
            ->givenName('Amelia')
            ->id('JDKYHBWT1D4F8MFH63DBMEN8Y4')
            ->note('updated customer note')
            ->preferences(
                CustomerPreferencesBuilder::init()
                    ->emailUnsubscribed(false)
                    ->build()
            )
            ->referenceId('YOUR_REFERENCE_ID')
            ->updatedAt('2016-05-15T20:21:55Z')
            ->version(3)
            ->build()
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

