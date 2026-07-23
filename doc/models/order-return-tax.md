
# Order Return Tax

Represents a tax being returned that applies to one or more return line items in an order.

Fixed-amount, order-scoped taxes are distributed across all non-zero return line item totals.
The amount distributed to each return line item is relative to that item’s contribution to the
order subtotal.

## Structure

`OrderReturnTax`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `appliedMoney` | [`?Money`](../../doc/models/money.md) | Optional | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getAppliedMoney(): ?Money | setAppliedMoney(?Money appliedMoney): void |
| `catalogObjectId` | `?string` | Optional | The catalog object ID referencing [CatalogTax](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogTax).<br><br>**Constraints**: *Maximum Length*: `192` | getCatalogObjectId(): ?string | setCatalogObjectId(?string catalogObjectId): void |
| `catalogVersion` | `?int` | Optional | The version of the catalog object that this tax references. | getCatalogVersion(): ?int | setCatalogVersion(?int catalogVersion): void |
| `name` | `?string` | Optional | The tax's name.<br><br>**Constraints**: *Maximum Length*: `255` | getName(): ?string | setName(?string name): void |
| `percentage` | `?string` | Optional | The percentage of the tax, as a string representation of a decimal number.<br>For example, a value of `"7.25"` corresponds to a percentage of 7.25%.<br><br>**Constraints**: *Maximum Length*: `10` | getPercentage(): ?string | setPercentage(?string percentage): void |
| `scope` | `?string` | Optional | Indicates the level at which the `OrderReturnTax` applies. For `ORDER` scoped<br>taxes, Square generates references in `applied_taxes` on all<br>`OrderReturnLineItem`s. For `LINE_ITEM` scoped taxes, the tax is only applied to<br>`OrderReturnLineItem`s with references in their `applied_discounts` field. | getScope(): ?string | setScope(?string scope): void |
| `sourceTaxUid` | `?string` | Optional | The tax `uid` from the order that contains the original tax charge.<br><br>**Constraints**: *Maximum Length*: `60` | getSourceTaxUid(): ?string | setSourceTaxUid(?string sourceTaxUid): void |
| `type` | `?string` | Optional | Indicates the calculation method used to apply the tax. | getType(): ?string | setType(?string type): void |
| `uid` | `?string` | Optional | A unique ID that identifies the returned tax only within this order.<br><br>**Constraints**: *Maximum Length*: `60` | getUid(): ?string | setUid(?string uid): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\OrderReturnTaxBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;

$orderReturnTax = OrderReturnTaxBuilder::init()
    ->appliedMoney(
        MoneyBuilder::init()
            ->amount(196)
            ->currency('currency8')
            ->build()
    )
    ->catalogObjectId('catalog_object_id2')
    ->catalogVersion(44)
    ->name('name4')
    ->percentage('percentage2')
    ->build();
```

