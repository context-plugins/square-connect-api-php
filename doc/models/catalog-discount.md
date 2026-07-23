
# Catalog Discount

A discount applicable to items.

## Structure

`CatalogDiscount`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amountMoney` | [`?Money`](../../doc/models/money.md) | Optional | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getAmountMoney(): ?Money | setAmountMoney(?Money amountMoney): void |
| `discountType` | `?string` | Optional | Indicates whether the discount is a fixed amount or percentage, or entered at the time of sale. | getDiscountType(): ?string | setDiscountType(?string discountType): void |
| `labelColor` | `?string` | Optional | The color of the discount display label in the Square Point of Sale app. This must be a valid hex color code. | getLabelColor(): ?string | setLabelColor(?string labelColor): void |
| `modifyTaxBasis` | `?string` | Optional | Indicates whether this discount should reduce the price used to calculate tax.<br><br>Most discounts should use `MODIFY_TAX_BASIS`. However, in some circumstances taxes must<br>be calculated based on an item's price, ignoring a particular discount. For example,<br>in many US jurisdictions, a manufacturer coupon or instant rebate reduces the price a<br>customer pays but does not reduce the sale price used to calculate how much sales tax is<br>due. In this case, the discount representing that manufacturer coupon should have<br>`DO_NOT_MODIFY_TAX_BASIS` for this field.<br><br>If you are unsure whether you need to use this field, consult your tax professional. | getModifyTaxBasis(): ?string | setModifyTaxBasis(?string modifyTaxBasis): void |
| `name` | `?string` | Optional | The discount name. This is a searchable attribute for use in applicable query filters, and its value length is of Unicode code points.<br><br>**Constraints**: *Maximum Length*: `255` | getName(): ?string | setName(?string name): void |
| `percentage` | `?string` | Optional | The percentage of the discount as a string representation of a decimal number, using a `.` as the decimal<br>separator and without a `%` sign. A value of `7.5` corresponds to `7.5%`. Specify a percentage of `0` if `discount_type`<br>is `VARIABLE_PERCENTAGE`.<br><br>Do not use this field for amount-based or variable discounts. | getPercentage(): ?string | setPercentage(?string percentage): void |
| `pinRequired` | `?bool` | Optional | Indicates whether a mobile staff member needs to enter their PIN to apply the<br>discount to a payment in the Square Point of Sale app. | getPinRequired(): ?bool | setPinRequired(?bool pinRequired): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CatalogDiscountBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;

$catalogDiscount = CatalogDiscountBuilder::init()
    ->amountMoney(
        MoneyBuilder::init()
            ->amount(186)
            ->currency('currency8')
            ->build()
    )
    ->discountType('discount_type8')
    ->labelColor('label_color2')
    ->modifyTaxBasis('modify_tax_basis8')
    ->name('name0')
    ->build();
```

