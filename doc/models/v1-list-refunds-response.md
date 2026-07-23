
# V1 List Refunds Response

## Structure

`V1ListRefundsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `items` | [`?(V1Refund[])`](../../doc/models/v1-refund.md) | Optional | - | getItems(): ?array | setItems(?array items): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\V1ListRefundsResponseBuilder;
use SquareConnectAPILib\Models\Builders\V1RefundBuilder;

$v1ListRefundsResponse = V1ListRefundsResponseBuilder::init()
    ->items(
        [
            V1RefundBuilder::init()
                ->createdAt('created_at6')
                ->isExchange(false)
                ->merchantId('merchant_id8')
                ->paymentId('payment_id8')
                ->processedAt('processed_at8')
                ->build()
        ]
    )
    ->build();
```

