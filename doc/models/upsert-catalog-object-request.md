
# Upsert Catalog Object Request

## Structure

`UpsertCatalogObjectRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `idempotencyKey` | `string` | Required | A value you specify that uniquely identifies this<br>request among all your requests. A common way to create<br>a valid idempotency key is to use a Universally unique<br>identifier (UUID).<br><br>If you're unsure whether a particular request was successful,<br>you can reattempt it with the same idempotency key without<br>worrying about creating duplicate objects.<br><br>See [Idempotency](https://developer.squareup.com/docs/basics/api101/idempotency) for more information.<br><br>**Constraints**: *Minimum Length*: `1` | getIdempotencyKey(): string | setIdempotencyKey(string idempotencyKey): void |
| `object` | [`CatalogObject`](../../doc/models/catalog-object.md) | Required | The wrapper object for the Catalog entries of a given object type.<br><br>The type of a particular `CatalogObject` is determined by the value of the<br>`type` attribute and only the corresponding data attribute can be set on the `CatalogObject` instance.<br>For example, the following list shows some instances of `CatalogObject` of a given `type` and<br>their corresponding data attribute that can be set:<br><br>- For a `CatalogObject` of the `ITEM` type, set the `item_data` attribute to yield the `CatalogItem` object.<br>- For a `CatalogObject` of the `ITEM_VARIATION` type, set the `item_variation_data` attribute to yield the `CatalogItemVariation` object.<br>- For a `CatalogObject` of the `MODIFIER` type, set the `modifier_data` attribute to yield the `CatalogModifier` object.<br>- For a `CatalogObject` of the `MODIFIER_LIST` type, set the `modifier_list_data` attribute to yield the `CatalogModifierList` object.<br>- For a `CatalogObject` of the `CATEGORY` type, set the `category_data` attribute to yield the `CatalogCategory` object.<br>- For a `CatalogObject` of the `DISCOUNT` type, set the `discount_data` attribute to yield the `CatalogDiscount` object.<br>- For a `CatalogObject` of the `TAX` type, set the `tax_data` attribute to yield the `CatalogTax` object.<br>- For a `CatalogObject` of the `IMAGE` type, set the `image_data` attribute to yield the `CatalogImageData`  object.<br>- For a `CatalogObject` of the `QUICK_AMOUNTS_SETTINGS` type, set the `quick_amounts_settings_data` attribute to yield the `CatalogQuickAmountsSettings` object.<br>- For a `CatalogObject` of the `PRICING_RULE` type, set the `pricing_rule_data` attribute to yield the `CatalogPricingRule` object.<br>- For a `CatalogObject` of the `TIME_PERIOD` type, set the `time_period_data` attribute to yield the `CatalogTimePeriod` object.<br>- For a `CatalogObject` of the `PRODUCT_SET` type, set the `product_set_data` attribute to yield the `CatalogProductSet`  object.<br>- For a `CatalogObject` of the `SUBSCRIPTION_PLAN` type, set the `subscription_plan_data` attribute to yield the `CatalogSubscriptionPlan` object.<br><br>For a more detailed discussion of the Catalog data model, please see the<br>[Design a Catalog](https://developer.squareup.com/docs/catalog-api/design-a-catalog) guide. | getObject(): CatalogObject | setObject(CatalogObject object): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\UpsertCatalogObjectRequestBuilder;
use SquareConnectAPILib\Models\Builders\CatalogObjectBuilder;
use SquareConnectAPILib\Models\Builders\CatalogV1IdBuilder;
use SquareConnectAPILib\Models\Builders\CatalogCategoryBuilder;
use SquareConnectAPILib\Models\Builders\CatalogCustomAttributeDefinitionBuilder;
use SquareConnectAPILib\Models\Builders\CatalogCustomAttributeDefinitionNumberConfigBuilder;
use SquareConnectAPILib\Models\Builders\CatalogCustomAttributeValueBuilder;
use SquareConnectAPILib\Models\Builders\CatalogDiscountBuilder;
use SquareConnectAPILib\Models\Builders\CatalogItemBuilder;
use SquareConnectAPILib\Models\Builders\CatalogModifierBuilder;
use SquareConnectAPILib\Models\Builders\CatalogModifierListBuilder;
use SquareConnectAPILib\Models\Builders\CatalogTaxBuilder;

$upsertCatalogObjectRequest = UpsertCatalogObjectRequestBuilder::init(
    'idempotency_key6',
    CatalogObjectBuilder::init(
        'id2',
        'type8'
    )
        ->absentAtLocationIds(
            [
                'absent_at_location_ids3'
            ]
        )
        ->catalogV1Ids(
            [
                CatalogV1IdBuilder::init()
                    ->catalogV1Id('catalog_v1_id4')
                    ->locationId('location_id4')
                    ->build()
            ]
        )
        ->categoryData(
            CatalogCategoryBuilder::init()
                ->name('name4')
                ->build()
        )
        ->customAttributeDefinitionData(
            CatalogCustomAttributeDefinitionBuilder::init(
                [
                    'allowed_object_types8',
                    'allowed_object_types7',
                    'allowed_object_types6'
                ],
                'name8',
                'type2'
            )
                ->appVisibility('app_visibility8')
                ->customAttributeUsageCount(142)
                ->description('description8')
                ->key('key8')
                ->numberConfig(
                    CatalogCustomAttributeDefinitionNumberConfigBuilder::init()
                        ->precision(5)
                        ->build()
                )
                ->build()
        )
        ->customAttributeValues(
            [
                'key0' => CatalogCustomAttributeValueBuilder::init()
                    ->booleanValue(false)
                    ->customAttributeDefinitionId('custom_attribute_definition_id4')
                    ->key('key8')
                    ->name('name8')
                    ->numberValue('number_value8')
                    ->build(),
                'key1' => CatalogCustomAttributeValueBuilder::init()
                    ->booleanValue(false)
                    ->customAttributeDefinitionId('custom_attribute_definition_id4')
                    ->key('key8')
                    ->name('name8')
                    ->numberValue('number_value8')
                    ->build()
            ]
        )
        ->discountData(
            CatalogDiscountBuilder::init()->build()
        )
        ->itemData(
            CatalogItemBuilder::init()->build()
        )
        ->modifierData(
            CatalogModifierBuilder::init()->build()
        )
        ->modifierListData(
            CatalogModifierListBuilder::init()->build()
        )
        ->taxData(
            CatalogTaxBuilder::init()->build()
        )->build()
)->build();
```

