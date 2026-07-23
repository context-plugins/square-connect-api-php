
# V1 List Orders Response

## Structure

`V1ListOrdersResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `items` | [`?(V1Order[])`](../../doc/models/v1-order.md) | Optional | - | getItems(): ?array | setItems(?array items): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\V1ListOrdersResponseBuilder;
use SquareConnectAPILib\Models\Builders\V1OrderBuilder;

$v1ListOrdersResponse = V1ListOrdersResponseBuilder::init()
    ->items(
        [
            V1OrderBuilder::init()
                ->btcPriceSatoshi(39.42)
                ->btcReceiveAddress('btc_receive_address4')
                ->buyerEmail('buyer_email0')
                ->buyerNote('buyer_note0')
                ->canceledNote('canceled_note2')
                ->build(),
            V1OrderBuilder::init()
                ->btcPriceSatoshi(39.42)
                ->btcReceiveAddress('btc_receive_address4')
                ->buyerEmail('buyer_email0')
                ->buyerNote('buyer_note0')
                ->canceledNote('canceled_note2')
                ->build()
        ]
    )
    ->build();
```

