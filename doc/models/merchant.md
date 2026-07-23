
# Merchant

Represents a Square seller.

## Structure

`Merchant`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `businessName` | `?string` | Optional | The business name of the merchant. | getBusinessName(): ?string | setBusinessName(?string businessName): void |
| `country` | `string` | Required | The country code associated with the merchant account, in ISO 3166 format. | getCountry(): string | setCountry(string country): void |
| `currency` | `?string` | Optional | The currency associated with the merchant account, in ISO 4217 format. | getCurrency(): ?string | setCurrency(?string currency): void |
| `id` | `?string` | Optional | The Square-issued ID of the merchant. | getId(): ?string | setId(?string id): void |
| `languageCode` | `?string` | Optional | The language code associated with the merchant account, in BCP 47 format. | getLanguageCode(): ?string | setLanguageCode(?string languageCode): void |
| `mainLocationId` | `?string` | Optional | The ID of the main `Location` for this merchant. | getMainLocationId(): ?string | setMainLocationId(?string mainLocationId): void |
| `status` | `?string` | Optional | The merchant status, active or inactive. | getStatus(): ?string | setStatus(?string status): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\MerchantBuilder;

$merchant = MerchantBuilder::init(
    'country8'
)
    ->businessName('business_name8')
    ->currency('currency4')
    ->id('id4')
    ->languageCode('language_code2')
    ->mainLocationId('main_location_id4')
    ->build();
```

