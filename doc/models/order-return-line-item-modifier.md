
# Order Return Line Item Modifier

A line item modifier being returned.

## Structure

`OrderReturnLineItemModifier`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `basePriceMoney` | [`?Money`](../../doc/models/money.md) | Optional | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getBasePriceMoney(): ?Money | setBasePriceMoney(?Money basePriceMoney): void |
| `catalogObjectId` | `?string` | Optional | The catalog object ID referencing [CatalogModifier](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogModifier).<br><br>**Constraints**: *Maximum Length*: `192` | getCatalogObjectId(): ?string | setCatalogObjectId(?string catalogObjectId): void |
| `catalogVersion` | `?int` | Optional | The version of the catalog object that this line item modifier references. | getCatalogVersion(): ?int | setCatalogVersion(?int catalogVersion): void |
| `name` | `?string` | Optional | The name of the item modifier.<br><br>**Constraints**: *Maximum Length*: `255` | getName(): ?string | setName(?string name): void |
| `sourceModifierUid` | `?string` | Optional | The modifier `uid` from the order's line item that contains the<br>original sale of this line item modifier.<br><br>**Constraints**: *Maximum Length*: `60` | getSourceModifierUid(): ?string | setSourceModifierUid(?string sourceModifierUid): void |
| `totalPriceMoney` | [`?Money`](../../doc/models/money.md) | Optional | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getTotalPriceMoney(): ?Money | setTotalPriceMoney(?Money totalPriceMoney): void |
| `uid` | `?string` | Optional | A unique ID that identifies the return modifier only within this order.<br><br>**Constraints**: *Maximum Length*: `60` | getUid(): ?string | setUid(?string uid): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\OrderReturnLineItemModifierBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;

$orderReturnLineItemModifier = OrderReturnLineItemModifierBuilder::init()
    ->basePriceMoney(
        MoneyBuilder::init()
            ->amount(114)
            ->currency('currency4')
            ->build()
    )
    ->catalogObjectId('catalog_object_id6')
    ->catalogVersion(128)
    ->name('name0')
    ->sourceModifierUid('source_modifier_uid6')
    ->build();
```

