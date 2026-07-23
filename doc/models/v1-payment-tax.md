
# V1 Payment Tax

V1PaymentTax

## Structure

`V1PaymentTax`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `appliedMoney` | [`?V1Money`](../../doc/models/v1-money.md) | Optional | - | getAppliedMoney(): ?V1Money | setAppliedMoney(?V1Money appliedMoney): void |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `feeId` | `?string` | Optional | The ID of the tax, if available. Taxes applied in older versions of Square Register might not have an ID. | getFeeId(): ?string | setFeeId(?string feeId): void |
| `inclusionType` | `?string` | Optional | Whether the tax is an ADDITIVE tax or an INCLUSIVE tax. | getInclusionType(): ?string | setInclusionType(?string inclusionType): void |
| `name` | `?string` | Optional | The merchant-defined name of the tax. | getName(): ?string | setName(?string name): void |
| `rate` | `?string` | Optional | The rate of the tax, as a string representation of a decimal number. A value of 0.07 corresponds to a rate of 7%. | getRate(): ?string | setRate(?string rate): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\V1PaymentTaxBuilder;
use SquareConnectAPILib\Models\Builders\V1MoneyBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;

$v1PaymentTax = V1PaymentTaxBuilder::init()
    ->appliedMoney(
        V1MoneyBuilder::init()
            ->amount(196)
            ->currencyCode('currency_code4')
            ->build()
    )
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
    ->feeId('fee_id4')
    ->inclusionType('inclusion_type2')
    ->name('name6')
    ->build();
```

