
# List Merchants Response

The response object returned by the [ListMerchant](https://developer.squareup.com/reference/square_2021-08-18/merchants-api/list-merchants) endpoint.

## Structure

`ListMerchantsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cursor` | `?int` | Optional | If the  response is truncated, the cursor to use in next  request to fetch next set of objects. | getCursor(): ?int | setCursor(?int cursor): void |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Information on errors encountered during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `merchant` | [`?(Merchant[])`](../../doc/models/merchant.md) | Optional | The requested `Merchant` entities. | getMerchant(): ?array | setMerchant(?array merchant): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\ListMerchantsResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\MerchantBuilder;

$listMerchantsResponse = ListMerchantsResponseBuilder::init()
    ->cursor(34)
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
    ->merchant(
        [
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
        ]
    )
    ->build();
```

