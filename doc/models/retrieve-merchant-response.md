
# Retrieve Merchant Response

The response object returned by the [RetrieveMerchant](https://developer.squareup.com/reference/square_2021-08-18/merchants-api/retrieve-merchant) endpoint.

## Structure

`RetrieveMerchantResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Information on errors encountered during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `merchant` | [`?Merchant`](../../doc/models/merchant.md) | Optional | Represents a Square seller. | getMerchant(): ?Merchant | setMerchant(?Merchant merchant): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\RetrieveMerchantResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\MerchantBuilder;

$retrieveMerchantResponse = RetrieveMerchantResponseBuilder::init()
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
    ->merchant(
        MerchantBuilder::init(
            'US'
        )
            ->businessName('Apple A Day')
            ->currency('USD')
            ->id('DM7VKY8Q63GNP')
            ->languageCode('en-US')
            ->mainLocationId('9A65CGC72ZQG1')
            ->status('ACTIVE')
            ->build()
    )
    ->build();
```

