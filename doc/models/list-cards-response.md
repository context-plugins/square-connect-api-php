
# List Cards Response

Defines the fields that are included in the response body of
a request to the [ListCards](#endpoint-cards-listcards) endpoint.

Note: if there are errors processing the request, the card field will not be
present.

## Structure

`ListCardsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cards` | [`?(Card[])`](../../doc/models/card.md) | Optional | The requested list of `Card`s. | getCards(): ?array | setCards(?array cards): void |
| `cursor` | `?string` | Optional | The pagination cursor to be used in a subsequent request. If empty,<br>this is the final response.<br><br>See [Pagination](https://developer.squareup.com/docs/basics/api101/pagination) for more information. | getCursor(): ?string | setCursor(?string cursor): void |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Information on errors encountered during the request. | getErrors(): ?array | setErrors(?array errors): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\ListCardsResponseBuilder;
use SquareConnectAPILib\Models\Builders\CardBuilder;
use SquareConnectAPILib\Models\Builders\AddressBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;

$listCardsResponse = ListCardsResponseBuilder::init()
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
    ->cursor('cursor8')
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

