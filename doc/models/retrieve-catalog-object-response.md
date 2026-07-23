
# Retrieve Catalog Object Response

## Structure

`RetrieveCatalogObjectResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `object` | [`?CatalogObject`](../../doc/models/catalog-object.md) | Optional | The wrapper object for the Catalog entries of a given object type.<br><br>The type of a particular `CatalogObject` is determined by the value of the<br>`type` attribute and only the corresponding data attribute can be set on the `CatalogObject` instance.<br>For example, the following list shows some instances of `CatalogObject` of a given `type` and<br>their corresponding data attribute that can be set:<br><br>- For a `CatalogObject` of the `ITEM` type, set the `item_data` attribute to yield the `CatalogItem` object.<br>- For a `CatalogObject` of the `ITEM_VARIATION` type, set the `item_variation_data` attribute to yield the `CatalogItemVariation` object.<br>- For a `CatalogObject` of the `MODIFIER` type, set the `modifier_data` attribute to yield the `CatalogModifier` object.<br>- For a `CatalogObject` of the `MODIFIER_LIST` type, set the `modifier_list_data` attribute to yield the `CatalogModifierList` object.<br>- For a `CatalogObject` of the `CATEGORY` type, set the `category_data` attribute to yield the `CatalogCategory` object.<br>- For a `CatalogObject` of the `DISCOUNT` type, set the `discount_data` attribute to yield the `CatalogDiscount` object.<br>- For a `CatalogObject` of the `TAX` type, set the `tax_data` attribute to yield the `CatalogTax` object.<br>- For a `CatalogObject` of the `IMAGE` type, set the `image_data` attribute to yield the `CatalogImageData`  object.<br>- For a `CatalogObject` of the `QUICK_AMOUNTS_SETTINGS` type, set the `quick_amounts_settings_data` attribute to yield the `CatalogQuickAmountsSettings` object.<br>- For a `CatalogObject` of the `PRICING_RULE` type, set the `pricing_rule_data` attribute to yield the `CatalogPricingRule` object.<br>- For a `CatalogObject` of the `TIME_PERIOD` type, set the `time_period_data` attribute to yield the `CatalogTimePeriod` object.<br>- For a `CatalogObject` of the `PRODUCT_SET` type, set the `product_set_data` attribute to yield the `CatalogProductSet`  object.<br>- For a `CatalogObject` of the `SUBSCRIPTION_PLAN` type, set the `subscription_plan_data` attribute to yield the `CatalogSubscriptionPlan` object.<br><br>For a more detailed discussion of the Catalog data model, please see the<br>[Design a Catalog](https://developer.squareup.com/docs/catalog-api/design-a-catalog) guide. | getObject(): ?CatalogObject | setObject(?CatalogObject object): void |
| `relatedObjects` | [`?(CatalogObject[])`](../../doc/models/catalog-object.md) | Optional | A list of `CatalogObject`s referenced by the object in the `object` field. | getRelatedObjects(): ?array | setRelatedObjects(?array relatedObjects): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\RetrieveCatalogObjectResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\CatalogObjectBuilder;
use SquareConnectAPILib\Models\Builders\CatalogV1IdBuilder;
use SquareConnectAPILib\Models\Builders\CatalogCategoryBuilder;
use SquareConnectAPILib\Models\Builders\CatalogCustomAttributeDefinitionBuilder;
use SquareConnectAPILib\Models\Builders\CatalogCustomAttributeDefinitionNumberConfigBuilder;
use SquareConnectAPILib\Models\Builders\CatalogCustomAttributeValueBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;
use SquareConnectAPILib\Models\Builders\CatalogItemBuilder;
use SquareConnectAPILib\Models\Builders\CatalogItemVariationBuilder;
use SquareConnectAPILib\Models\Builders\CatalogTaxBuilder;

$retrieveCatalogObjectResponse = RetrieveCatalogObjectResponseBuilder::init()
    ->errors(
        [
            ErrorBuilder::init(
                'category8',
                'code8'
            )
                ->detail('detail6')
                ->field('field4')
                ->build(),
            ErrorBuilder::init(
                'category8',
                'code8'
            )
                ->detail('detail6')
                ->field('field4')
                ->build(),
            ErrorBuilder::init(
                'category8',
                'code8'
            )
                ->detail('detail6')
                ->field('field4')
                ->build()
        ]
    )
    ->object(
        CatalogObjectBuilder::init(
            'W62UWFY35CWMYGVWK6TWJDNI',
            'ITEM'
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
                null
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
            ->isDeleted(false)
            ->itemData(
                CatalogItemBuilder::init()
                    ->categoryId('BJNQCF2FJ6S6UIDT65ABHLRX')
                    ->description('Hot Leaf Juice')
                    ->name('Tea')
                    ->taxIds(
                        [
                            'HURXQOOAIC4IZSI2BEXQRYFY'
                        ]
                    )
                    ->variations(
                        [
                            CatalogObjectBuilder::init(
                                '2TZFAOHWGG7PAK2QEXWYPZSP',
                                'ITEM_VARIATION'
                            )
                                ->isDeleted(false)
                                ->itemVariationData(
                                    CatalogItemVariationBuilder::init()
                                        ->itemId('W62UWFY35CWMYGVWK6TWJDNI')
                                        ->name('Mug')
                                        ->ordinal(0)
                                        ->priceMoney(
                                            MoneyBuilder::init()
                                                ->amount(150)
                                                ->currency('USD')
                                                ->build()
                                        )
                                        ->pricingType('FIXED_PRICING')
                                        ->build()
                                )
                                ->presentAtAllLocations(true)
                                ->updatedAt('2016-11-16T22:25:24.878Z')
                                ->version(1479335124878)
                                ->build()
                        ]
                    )
                    ->build()
            )
            ->presentAtAllLocations(true)
            ->updatedAt('2016-11-16T22:25:24.878Z')
            ->version(1479335124878)
            ->build()
    )
    ->relatedObjects(
        [
            CatalogObjectBuilder::init(
                'BJNQCF2FJ6S6UIDT65ABHLRX',
                'CATEGORY'
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
                        ->name('Beverages')
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
                ->isDeleted(false)
                ->presentAtAllLocations(true)
                ->updatedAt('2016-11-16T22:25:24.878Z')
                ->version(1479335124878)
                ->build(),
            CatalogObjectBuilder::init(
                'HURXQOOAIC4IZSI2BEXQRYFY',
                'TAX'
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
                    CatalogCategoryBuilder::init()->build()
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
                ->isDeleted(false)
                ->presentAtAllLocations(true)
                ->taxData(
                    CatalogTaxBuilder::init()
                        ->calculationPhase('TAX_SUBTOTAL_PHASE')
                        ->enabled(true)
                        ->inclusionType('ADDITIVE')
                        ->name('Sales Tax')
                        ->percentage('5.0')
                        ->build()
                )
                ->updatedAt('2016-11-16T22:25:24.878Z')
                ->version(1479335124878)
                ->build()
        ]
    )
    ->build();
```

