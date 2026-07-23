
# Order Return Discount

Represents a discount being returned that applies to one or more return line items in an
order.

Fixed-amount, order-scoped discounts are distributed across all non-zero return line item totals.
The amount distributed to each return line item is relative to that item’s contribution to the
order subtotal.

## Structure

`OrderReturnDiscount`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amountMoney` | [`?Money`](../../doc/models/money.md) | Optional | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getAmountMoney(): ?Money | setAmountMoney(?Money amountMoney): void |
| `appliedMoney` | [`?Money`](../../doc/models/money.md) | Optional | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getAppliedMoney(): ?Money | setAppliedMoney(?Money appliedMoney): void |
| `catalogObjectId` | `?string` | Optional | The catalog object ID referencing [CatalogDiscount](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogDiscount).<br><br>**Constraints**: *Maximum Length*: `192` | getCatalogObjectId(): ?string | setCatalogObjectId(?string catalogObjectId): void |
| `catalogVersion` | `?int` | Optional | The version of the catalog object that this discount references. | getCatalogVersion(): ?int | setCatalogVersion(?int catalogVersion): void |
| `name` | `?string` | Optional | The discount's name.<br><br>**Constraints**: *Maximum Length*: `255` | getName(): ?string | setName(?string name): void |
| `percentage` | `?string` | Optional | The percentage of the tax, as a string representation of a decimal number.<br>A value of `"7.25"` corresponds to a percentage of 7.25%.<br><br>`percentage` is not set for amount-based discounts.<br><br>**Constraints**: *Maximum Length*: `10` | getPercentage(): ?string | setPercentage(?string percentage): void |
| `scope` | `?string` | Optional | Indicates the level at which the `OrderReturnDiscount` applies. For `ORDER` scoped<br>discounts, the server generates references in `applied_discounts` on all<br>`OrderReturnLineItem`s. For `LINE_ITEM` scoped discounts, the discount is only applied to<br>`OrderReturnLineItem`s with references in their `applied_discounts` field. | getScope(): ?string | setScope(?string scope): void |
| `sourceDiscountUid` | `?string` | Optional | The discount `uid` from the order that contains the original application of this discount.<br><br>**Constraints**: *Maximum Length*: `60` | getSourceDiscountUid(): ?string | setSourceDiscountUid(?string sourceDiscountUid): void |
| `type` | `?string` | Optional | The type of the discount. If it is created by the API, it is `FIXED_PERCENTAGE` or `FIXED_AMOUNT`.<br><br>Discounts that do not reference a catalog object ID must have a type of<br>`FIXED_PERCENTAGE` or `FIXED_AMOUNT`. | getType(): ?string | setType(?string type): void |
| `uid` | `?string` | Optional | A unique ID that identifies the returned discount only within this order.<br><br>**Constraints**: *Maximum Length*: `60` | getUid(): ?string | setUid(?string uid): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\OrderReturnDiscountBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;

$orderReturnDiscount = OrderReturnDiscountBuilder::init()
    ->amountMoney(
        MoneyBuilder::init()
            ->amount(186)
            ->currency('currency8')
            ->build()
    )
    ->appliedMoney(
        MoneyBuilder::init()
            ->amount(196)
            ->currency('currency8')
            ->build()
    )
    ->catalogObjectId('catalog_object_id0')
    ->catalogVersion(92)
    ->name('name6')
    ->build();
```

