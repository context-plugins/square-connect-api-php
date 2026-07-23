
# Create Customer Request

Defines the body parameters that can be included in a request to the
`CreateCustomer` endpoint.

## Structure

`CreateCustomerRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `address` | [`?Address`](../../doc/models/address.md) | Optional | Represents a postal address in a country. The address format is based<br>on an [open-source library from Google](https://github.com/google/libaddressinput). For more information,<br>see [AddressValidationMetadata](https://github.com/google/libaddressinput/wiki/AddressValidationMetadata).<br>This format has dedicated fields for four address components: postal code,<br>locality (city), administrative district (state, prefecture, or province), and<br>sublocality (town or village). These components have dedicated fields in the<br>`Address` object because software sometimes behaves differently based on them.<br>For example, sales tax software may charge different amounts of sales tax<br>based on the postal code, and some software is only available in<br>certain states due to compliance reasons.<br><br>For the remaining address components, the `Address` type provides the<br>`address_line_1` and `address_line_2` fields for free-form data entry.<br>These fields are free-form because the remaining address components have<br>too many variations around the world and typical software does not parse<br>these components. These fields enable users to enter anything they want.<br><br>Note that, in the current implementation, all other `Address` type fields are blank.<br>These include `address_line_3`, `sublocality_2`, `sublocality_3`,<br>`administrative_district_level_2`, `administrative_district_level_3`,<br>`first_name`, `last_name`, and `organization`.<br><br>When it comes to localization, the seller's language preferences<br>(see [Language preferences](https://developer.squareup.com/docs/locations-api#location-specific-and-seller-level-language-preferences))<br>are ignored for addresses. Even though Square products (such as Square Point of Sale<br>and the Seller Dashboard) mostly use a seller's language preference in<br>communication, when it comes to addresses, they will use English for a US address,<br>Japanese for an address in Japan, and so on. | getAddress(): ?Address | setAddress(?Address address): void |
| `birthday` | `?string` | Optional | The birthday associated with the customer profile, in RFC 3339 format. The year is optional. The timezone and time are not allowed.<br>For example, `0000-09-21T00:00:00-00:00` represents a birthday on September 21 and `1998-09-21T00:00:00-00:00` represents a birthday on September 21, 1998.<br>You can also specify this value in `YYYY-MM-DD` format. | getBirthday(): ?string | setBirthday(?string birthday): void |
| `companyName` | `?string` | Optional | A business name associated with the customer profile. | getCompanyName(): ?string | setCompanyName(?string companyName): void |
| `emailAddress` | `?string` | Optional | The email address associated with the customer profile. | getEmailAddress(): ?string | setEmailAddress(?string emailAddress): void |
| `familyName` | `?string` | Optional | The family name (that is, the last name) associated with the customer profile. | getFamilyName(): ?string | setFamilyName(?string familyName): void |
| `givenName` | `?string` | Optional | The given name (that is, the first name) associated with the customer profile. | getGivenName(): ?string | setGivenName(?string givenName): void |
| `idempotencyKey` | `?string` | Optional | The idempotency key for the request.    For more information, see<br>[Idempotency](https://developer.squareup.com/docs/working-with-apis/idempotency). | getIdempotencyKey(): ?string | setIdempotencyKey(?string idempotencyKey): void |
| `nickname` | `?string` | Optional | A nickname for the customer profile. | getNickname(): ?string | setNickname(?string nickname): void |
| `note` | `?string` | Optional | A custom note associated with the customer profile. | getNote(): ?string | setNote(?string note): void |
| `phoneNumber` | `?string` | Optional | The 11-digit phone number associated with the customer profile. | getPhoneNumber(): ?string | setPhoneNumber(?string phoneNumber): void |
| `referenceId` | `?string` | Optional | An optional second ID used to associate the customer profile with an<br>entity in another system. | getReferenceId(): ?string | setReferenceId(?string referenceId): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CreateCustomerRequestBuilder;
use SquareConnectAPILib\Models\Builders\AddressBuilder;

$createCustomerRequest = CreateCustomerRequestBuilder::init()
    ->address(
        AddressBuilder::init()
            ->addressLine1('address_line_16')
            ->addressLine2('address_line_26')
            ->addressLine3('address_line_32')
            ->administrativeDistrictLevel1('administrative_district_level_10')
            ->administrativeDistrictLevel2('administrative_district_level_28')
            ->build()
    )
    ->birthday('birthday4')
    ->companyName('company_name0')
    ->emailAddress('email_address2')
    ->familyName('family_name2')
    ->build();
```

