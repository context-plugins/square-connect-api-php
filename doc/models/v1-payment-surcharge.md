
# V1 Payment Surcharge

V1PaymentSurcharge

## Structure

`V1PaymentSurcharge`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amountMoney` | [`?V1Money`](../../doc/models/v1-money.md) | Optional | - | getAmountMoney(): ?V1Money | setAmountMoney(?V1Money amountMoney): void |
| `appliedMoney` | [`?V1Money`](../../doc/models/v1-money.md) | Optional | - | getAppliedMoney(): ?V1Money | setAppliedMoney(?V1Money appliedMoney): void |
| `name` | `?string` | Optional | The name of the surcharge. | getName(): ?string | setName(?string name): void |
| `rate` | `?string` | Optional | The amount of the surcharge as a percentage. The percentage is provided as a string representing the decimal equivalent of the percentage. For example, "0.7" corresponds to a 7% surcharge. Exactly one of rate or amount_money should be set. | getRate(): ?string | setRate(?string rate): void |
| `surchargeId` | `?string` | Optional | A Square-issued unique identifier associated with the surcharge. | getSurchargeId(): ?string | setSurchargeId(?string surchargeId): void |
| `taxable` | `?bool` | Optional | Indicates whether the surcharge is taxable. | getTaxable(): ?bool | setTaxable(?bool taxable): void |
| `taxes` | [`?(V1PaymentTax[])`](../../doc/models/v1-payment-tax.md) | Optional | The list of taxes that should be applied to the surcharge. | getTaxes(): ?array | setTaxes(?array taxes): void |
| `type` | `?string` | Optional | Indicates the source of the surcharge. For example, if it was applied as an automatic gratuity for a large group. | getType(): ?string | setType(?string type): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\V1PaymentSurchargeBuilder;
use SquareConnectAPILib\Models\Builders\V1MoneyBuilder;

$v1PaymentSurcharge = V1PaymentSurchargeBuilder::init()
    ->amountMoney(
        V1MoneyBuilder::init()
            ->amount(186)
            ->currencyCode('currency_code4')
            ->build()
    )
    ->appliedMoney(
        V1MoneyBuilder::init()
            ->amount(196)
            ->currencyCode('currency_code4')
            ->build()
    )
    ->name('name8')
    ->rate('rate8')
    ->surchargeId('surcharge_id4')
    ->build();
```

