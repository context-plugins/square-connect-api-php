
# Loyalty Program Reward Definition

Provides details about the reward tier discount. DEPRECATED at version 2020-12-16. Discount details
are now defined using a catalog pricing rule and other catalog objects. For more information, see
[Get discount details for the reward](https://developer.squareup.com/docs/loyalty-api/overview#get-discount-details).

## Structure

`LoyaltyProgramRewardDefinition`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `catalogObjectIds` | `?(string[])` | Optional | The list of catalog objects to which this reward can be applied. They are either all item-variation ids or category ids, depending on the `type` field.<br>DEPRECATED at version 2020-12-16. You can find this information in the `product_set_data.product_ids_any` field<br>of the `PRODUCT_SET` catalog object referenced by the pricing rule. | getCatalogObjectIds(): ?array | setCatalogObjectIds(?array catalogObjectIds): void |
| `discountType` | `string` | Required | The type of discount the reward tier offers. DEPRECATED at version 2020-12-16. You can find this information<br>in the `discount_data.discount_type` field of the `DISCOUNT` catalog object referenced by the pricing rule. | getDiscountType(): string | setDiscountType(string discountType): void |
| `fixedDiscountMoney` | [`?Money`](../../doc/models/money.md) | Optional | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getFixedDiscountMoney(): ?Money | setFixedDiscountMoney(?Money fixedDiscountMoney): void |
| `maxDiscountMoney` | [`?Money`](../../doc/models/money.md) | Optional | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getMaxDiscountMoney(): ?Money | setMaxDiscountMoney(?Money maxDiscountMoney): void |
| `percentageDiscount` | `?string` | Optional | The fixed percentage of the discount. Present if `discount_type` is `FIXED_PERCENTAGE`.<br>For example, a 7.25% off discount will be represented as "7.25". DEPRECATED at version 2020-12-16. You can find this<br>information in the `discount_data.percentage` field of the `DISCOUNT` catalog object referenced by the pricing rule. | getPercentageDiscount(): ?string | setPercentageDiscount(?string percentageDiscount): void |
| `scope` | `string` | Required | Indicates the scope of the reward tier. DEPRECATED at version 2020-12-16. You can find this information in the<br>`discount_target_scope` field of the `PRICING_RULE` catalog object and the `product_set_data` field of the `PRODUCT_SET`<br>catalog object referenced by the pricing rule. For `ORDER` scopes, the target scope is `WHOLE_PURCHASE` and `all_products`<br>is true. For `ITEM_VARIATION` and `CATEGORY` scopes, the target scope is `LINE_ITEM` and `product_ids_any` is a list of<br>catalog object IDs of the given type. | getScope(): string | setScope(string scope): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\LoyaltyProgramRewardDefinitionBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;

$loyaltyProgramRewardDefinition = LoyaltyProgramRewardDefinitionBuilder::init(
    'discount_type4',
    'scope4'
)
    ->catalogObjectIds(
        [
            'catalog_object_ids0',
            'catalog_object_ids1'
        ]
    )
    ->fixedDiscountMoney(
        MoneyBuilder::init()
            ->amount(36)
            ->currency('currency4')
            ->build()
    )
    ->maxDiscountMoney(
        MoneyBuilder::init()
            ->amount(84)
            ->currency('currency0')
            ->build()
    )
    ->percentageDiscount('percentage_discount8')
    ->build();
```

