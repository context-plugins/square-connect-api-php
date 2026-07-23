
# Order Return Line Item

The line item being returned in an order.

## Structure

`OrderReturnLineItem`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `appliedDiscounts` | [`?(OrderLineItemAppliedDiscount[])`](../../doc/models/order-line-item-applied-discount.md) | Optional | The list of references to `OrderReturnDiscount` entities applied to the return line item. Each<br>`OrderLineItemAppliedDiscount` has a `discount_uid` that references the `uid` of a top-level<br>`OrderReturnDiscount` applied to the return line item. On reads, the applied amount<br>is populated. | getAppliedDiscounts(): ?array | setAppliedDiscounts(?array appliedDiscounts): void |
| `appliedTaxes` | [`?(OrderLineItemAppliedTax[])`](../../doc/models/order-line-item-applied-tax.md) | Optional | The list of references to `OrderReturnTax` entities applied to the return line item. Each<br>`OrderLineItemAppliedTax` has a `tax_uid` that references the `uid` of a top-level<br>`OrderReturnTax` applied to the return line item. On reads, the applied amount<br>is populated. | getAppliedTaxes(): ?array | setAppliedTaxes(?array appliedTaxes): void |
| `basePriceMoney` | [`?Money`](../../doc/models/money.md) | Optional | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getBasePriceMoney(): ?Money | setBasePriceMoney(?Money basePriceMoney): void |
| `catalogObjectId` | `?string` | Optional | The [CatalogItemVariation](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogItemVariation) ID applied to this return line item.<br><br>**Constraints**: *Maximum Length*: `192` | getCatalogObjectId(): ?string | setCatalogObjectId(?string catalogObjectId): void |
| `catalogVersion` | `?int` | Optional | The version of the catalog object that this line item references. | getCatalogVersion(): ?int | setCatalogVersion(?int catalogVersion): void |
| `grossReturnMoney` | [`?Money`](../../doc/models/money.md) | Optional | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getGrossReturnMoney(): ?Money | setGrossReturnMoney(?Money grossReturnMoney): void |
| `itemType` | `?string` | Optional | The type of line item: an itemized return, a non-itemized return (custom amount),<br>or the return of an unactivated gift card sale. | getItemType(): ?string | setItemType(?string itemType): void |
| `name` | `?string` | Optional | The name of the line item.<br><br>**Constraints**: *Maximum Length*: `512` | getName(): ?string | setName(?string name): void |
| `note` | `?string` | Optional | The note of the return line item.<br><br>**Constraints**: *Maximum Length*: `2000` | getNote(): ?string | setNote(?string note): void |
| `quantity` | `string` | Required | The quantity returned, formatted as a decimal number.<br>For example, `"3"`.<br><br>Line items with a `quantity_unit` can have non-integer quantities.<br>For example, `"1.70000"`.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `12` | getQuantity(): string | setQuantity(string quantity): void |
| `quantityUnit` | [`?OrderQuantityUnit`](../../doc/models/order-quantity-unit.md) | Optional | Contains the measurement unit for a quantity and a precision that<br>specifies the number of digits after the decimal point for decimal quantities. | getQuantityUnit(): ?OrderQuantityUnit | setQuantityUnit(?OrderQuantityUnit quantityUnit): void |
| `returnModifiers` | [`?(OrderReturnLineItemModifier[])`](../../doc/models/order-return-line-item-modifier.md) | Optional | The [CatalogModifier](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogModifier)s applied to this line item. | getReturnModifiers(): ?array | setReturnModifiers(?array returnModifiers): void |
| `sourceLineItemUid` | `?string` | Optional | The `uid` of the line item in the original sale order.<br><br>**Constraints**: *Maximum Length*: `60` | getSourceLineItemUid(): ?string | setSourceLineItemUid(?string sourceLineItemUid): void |
| `totalDiscountMoney` | [`?Money`](../../doc/models/money.md) | Optional | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getTotalDiscountMoney(): ?Money | setTotalDiscountMoney(?Money totalDiscountMoney): void |
| `totalMoney` | [`?Money`](../../doc/models/money.md) | Optional | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getTotalMoney(): ?Money | setTotalMoney(?Money totalMoney): void |
| `totalTaxMoney` | [`?Money`](../../doc/models/money.md) | Optional | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getTotalTaxMoney(): ?Money | setTotalTaxMoney(?Money totalTaxMoney): void |
| `uid` | `?string` | Optional | A unique ID for this return line-item entry.<br><br>**Constraints**: *Maximum Length*: `60` | getUid(): ?string | setUid(?string uid): void |
| `variationName` | `?string` | Optional | The name of the variation applied to this return line item.<br><br>**Constraints**: *Maximum Length*: `255` | getVariationName(): ?string | setVariationName(?string variationName): void |
| `variationTotalPriceMoney` | [`?Money`](../../doc/models/money.md) | Optional | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getVariationTotalPriceMoney(): ?Money | setVariationTotalPriceMoney(?Money variationTotalPriceMoney): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\OrderReturnLineItemBuilder;
use SquareConnectAPILib\Models\Builders\OrderLineItemAppliedDiscountBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;
use SquareConnectAPILib\Models\Builders\OrderLineItemAppliedTaxBuilder;

$orderReturnLineItem = OrderReturnLineItemBuilder::init(
    'quantity8'
)
    ->appliedDiscounts(
        [
            OrderLineItemAppliedDiscountBuilder::init(
                'discount_uid8'
            )
                ->appliedMoney(
                    MoneyBuilder::init()
                        ->amount(196)
                        ->currency('currency8')
                        ->build()
                )
                ->uid('uid6')
                ->build(),
            OrderLineItemAppliedDiscountBuilder::init(
                'discount_uid8'
            )
                ->appliedMoney(
                    MoneyBuilder::init()
                        ->amount(196)
                        ->currency('currency8')
                        ->build()
                )
                ->uid('uid6')
                ->build()
        ]
    )
    ->appliedTaxes(
        [
            OrderLineItemAppliedTaxBuilder::init(
                'tax_uid4'
            )
                ->appliedMoney(
                    MoneyBuilder::init()
                        ->amount(196)
                        ->currency('currency8')
                        ->build()
                )
                ->uid('uid0')
                ->build()
        ]
    )
    ->basePriceMoney(
        MoneyBuilder::init()
            ->amount(114)
            ->currency('currency4')
            ->build()
    )
    ->catalogObjectId('catalog_object_id4')
    ->catalogVersion(26)
    ->build();
```

