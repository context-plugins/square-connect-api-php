
# V1 Payment Itemization

Payment include an` itemizations` field that lists the items purchased,
along with associated fees, modifiers, and discounts. Each itemization has an
`itemization_type` field that indicates which of the following the itemization
represents:

<ul>
<li>An item variation from the merchant's item library</li>
<li>A custom monetary amount</li>
<li>
An action performed on a Square gift card, such as activating or
reloading it.
</li>
</ul>
*Note**: itemization information included in a `Payment` object reflects
details collected **at the time of the payment**. Details such as the name or
price of items might have changed since the payment was processed.

## Structure

`V1PaymentItemization`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `discountMoney` | [`?V1Money`](../../doc/models/v1-money.md) | Optional | - | getDiscountMoney(): ?V1Money | setDiscountMoney(?V1Money discountMoney): void |
| `discounts` | [`?(V1PaymentDiscount[])`](../../doc/models/v1-payment-discount.md) | Optional | All discounts applied to this itemization. | getDiscounts(): ?array | setDiscounts(?array discounts): void |
| `grossSalesMoney` | [`?V1Money`](../../doc/models/v1-money.md) | Optional | - | getGrossSalesMoney(): ?V1Money | setGrossSalesMoney(?V1Money grossSalesMoney): void |
| `itemDetail` | [`?V1PaymentItemDetail`](../../doc/models/v1-payment-item-detail.md) | Optional | V1PaymentItemDetail | getItemDetail(): ?V1PaymentItemDetail | setItemDetail(?V1PaymentItemDetail itemDetail): void |
| `itemVariationName` | `?string` | Optional | The name of the item variation purchased, if any. | getItemVariationName(): ?string | setItemVariationName(?string itemVariationName): void |
| `itemizationType` | `?string` | Optional | The type of purchase that the itemization represents, such as an ITEM or CUSTOM_AMOUNT | getItemizationType(): ?string | setItemizationType(?string itemizationType): void |
| `modifiers` | [`?(V1PaymentModifier[])`](../../doc/models/v1-payment-modifier.md) | Optional | All modifier options applied to this itemization. | getModifiers(): ?array | setModifiers(?array modifiers): void |
| `name` | `?string` | Optional | The item's name. | getName(): ?string | setName(?string name): void |
| `netSalesMoney` | [`?V1Money`](../../doc/models/v1-money.md) | Optional | - | getNetSalesMoney(): ?V1Money | setNetSalesMoney(?V1Money netSalesMoney): void |
| `notes` | `?string` | Optional | Notes entered by the merchant about the item at the time of payment, if any. | getNotes(): ?string | setNotes(?string notes): void |
| `quantity` | `?float` | Optional | The quantity of the item purchased. This can be a decimal value. | getQuantity(): ?float | setQuantity(?float quantity): void |
| `singleQuantityMoney` | [`?V1Money`](../../doc/models/v1-money.md) | Optional | - | getSingleQuantityMoney(): ?V1Money | setSingleQuantityMoney(?V1Money singleQuantityMoney): void |
| `taxes` | [`?(V1PaymentTax[])`](../../doc/models/v1-payment-tax.md) | Optional | All taxes applied to this itemization. | getTaxes(): ?array | setTaxes(?array taxes): void |
| `totalMoney` | [`?V1Money`](../../doc/models/v1-money.md) | Optional | - | getTotalMoney(): ?V1Money | setTotalMoney(?V1Money totalMoney): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\V1PaymentItemizationBuilder;
use SquareConnectAPILib\Models\Builders\V1MoneyBuilder;
use SquareConnectAPILib\Models\Builders\V1PaymentDiscountBuilder;
use SquareConnectAPILib\Models\Builders\V1PaymentItemDetailBuilder;

$v1PaymentItemization = V1PaymentItemizationBuilder::init()
    ->discountMoney(
        V1MoneyBuilder::init()
            ->amount(92)
            ->currencyCode('currency_code0')
            ->build()
    )
    ->discounts(
        [
            V1PaymentDiscountBuilder::init()
                ->appliedMoney(
                    V1MoneyBuilder::init()
                        ->amount(196)
                        ->currencyCode('currency_code4')
                        ->build()
                )
                ->discountId('discount_id2')
                ->name('name4')
                ->build(),
            V1PaymentDiscountBuilder::init()
                ->appliedMoney(
                    V1MoneyBuilder::init()
                        ->amount(196)
                        ->currencyCode('currency_code4')
                        ->build()
                )
                ->discountId('discount_id2')
                ->name('name4')
                ->build(),
            V1PaymentDiscountBuilder::init()
                ->appliedMoney(
                    V1MoneyBuilder::init()
                        ->amount(196)
                        ->currencyCode('currency_code4')
                        ->build()
                )
                ->discountId('discount_id2')
                ->name('name4')
                ->build()
        ]
    )
    ->grossSalesMoney(
        V1MoneyBuilder::init()
            ->amount(198)
            ->currencyCode('currency_code8')
            ->build()
    )
    ->itemDetail(
        V1PaymentItemDetailBuilder::init()
            ->categoryName('category_name0')
            ->itemId('item_id2')
            ->itemVariationId('item_variation_id2')
            ->sku('sku6')
            ->build()
    )
    ->itemVariationName('item_variation_name6')
    ->build();
```

