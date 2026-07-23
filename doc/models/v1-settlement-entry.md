
# V1 Settlement Entry

V1SettlementEntry

## Structure

`V1SettlementEntry`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amountMoney` | [`?V1Money`](../../doc/models/v1-money.md) | Optional | - | getAmountMoney(): ?V1Money | setAmountMoney(?V1Money amountMoney): void |
| `feeMoney` | [`?V1Money`](../../doc/models/v1-money.md) | Optional | - | getFeeMoney(): ?V1Money | setFeeMoney(?V1Money feeMoney): void |
| `paymentId` | `?string` | Optional | The settlement's unique identifier. | getPaymentId(): ?string | setPaymentId(?string paymentId): void |
| `type` | `?string` | Optional | The settlement's current status. | getType(): ?string | setType(?string type): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\V1SettlementEntryBuilder;
use SquareConnectAPILib\Models\Builders\V1MoneyBuilder;

$v1SettlementEntry = V1SettlementEntryBuilder::init()
    ->amountMoney(
        V1MoneyBuilder::init()
            ->amount(186)
            ->currencyCode('currency_code4')
            ->build()
    )
    ->feeMoney(
        V1MoneyBuilder::init()
            ->amount(108)
            ->currencyCode('currency_code6')
            ->build()
    )
    ->paymentId('payment_id4')
    ->type('type4')
    ->build();
```

