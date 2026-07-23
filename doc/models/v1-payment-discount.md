
# V1 Payment Discount

V1PaymentDiscount

## Structure

`V1PaymentDiscount`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `appliedMoney` | [`?V1Money`](../../doc/models/v1-money.md) | Optional | - | getAppliedMoney(): ?V1Money | setAppliedMoney(?V1Money appliedMoney): void |
| `discountId` | `?string` | Optional | The ID of the applied discount, if available. Discounts applied in older versions of Square Register might not have an ID. | getDiscountId(): ?string | setDiscountId(?string discountId): void |
| `name` | `?string` | Optional | The discount's name. | getName(): ?string | setName(?string name): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\V1PaymentDiscountBuilder;
use SquareConnectAPILib\Models\Builders\V1MoneyBuilder;

$v1PaymentDiscount = V1PaymentDiscountBuilder::init()
    ->appliedMoney(
        V1MoneyBuilder::init()
            ->amount(196)
            ->currencyCode('currency_code4')
            ->build()
    )
    ->discountId('discount_id0')
    ->name('name2')
    ->build();
```

