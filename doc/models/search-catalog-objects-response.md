
# Search Catalog Objects Response

## Structure

`SearchCatalogObjectsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cursor` | `?string` | Optional | The pagination cursor to be used in a subsequent request. If unset, this is the final response.<br>See [Pagination](https://developer.squareup.com/docs/basics/api101/pagination) for more information. | getCursor(): ?string | setCursor(?string cursor): void |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `latestTime` | `?string` | Optional | When the associated product catalog was last updated. Will<br>match the value for `end_time` or `cursor` if either field is included in the `SearchCatalog` request. | getLatestTime(): ?string | setLatestTime(?string latestTime): void |
| `objects` | [`?(CatalogObject[])`](../../doc/models/catalog-object.md) | Optional | The CatalogObjects returned. | getObjects(): ?array | setObjects(?array objects): void |
| `relatedObjects` | [`?(CatalogObject[])`](../../doc/models/catalog-object.md) | Optional | A list of CatalogObjects referenced by the objects in the `objects` field. | getRelatedObjects(): ?array | setRelatedObjects(?array relatedObjects): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\SearchCatalogObjectsResponseBuilder;
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

$searchCatalogObjectsResponse = SearchCatalogObjectsResponseBuilder::init()
    ->cursor('cursor4')
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
                ->build()
        ]
    )
    ->latestTime('latest_time4')
    ->objects(
        [
            CatalogObjectBuilder::init(
                'X5DZ5NWWAQ44CKBLKIFQGOWK',
                'ITEM'
            )
                ->absentAtLocationIds(
                    [
                        'absent_at_location_ids7',
                        'absent_at_location_ids8',
                        'absent_at_location_ids9'
                    ]
                )
                ->catalogV1Ids(
                    [
                        CatalogV1IdBuilder::init()
                            ->catalogV1Id('catalog_v1_id4')
                            ->locationId('location_id4')
                            ->build(),
                        CatalogV1IdBuilder::init()
                            ->catalogV1Id('catalog_v1_id4')
                            ->locationId('location_id4')
                            ->build(),
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
                        ->categoryId('E7CLE5RZZ744BHWVQQEAHI2C')
                        ->description('A delicious blend of black tea.')
                        ->name('Tea - Black')
                        ->productType('REGULAR')
                        ->taxIds(
                            [
                                'ZXITPM6RWHZ7GZ7EIP3YKECM'
                            ]
                        )
                        ->variations(
                            [
                                CatalogObjectBuilder::init(
                                    '5GSZPX6EU7MM75S57OONG3V5',
                                    'ITEM_VARIATION'
                                )
                                    ->isDeleted(false)
                                    ->itemVariationData(
                                        CatalogItemVariationBuilder::init()
                                            ->itemId('X5DZ5NWWAQ44CKBLKIFQGOWK')
                                            ->name('Regular')
                                            ->ordinal(1)
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
                                    ->updatedAt('2017-10-26T15:27:31.626Z')
                                    ->version(1509031651626)
                                    ->build(),
                                CatalogObjectBuilder::init(
                                    'XVLBN7DU6JTWHJTG5F265B43',
                                    'ITEM_VARIATION'
                                )
                                    ->isDeleted(false)
                                    ->itemVariationData(
                                        CatalogItemVariationBuilder::init()
                                            ->itemId('X5DZ5NWWAQ44CKBLKIFQGOWK')
                                            ->name('Large')
                                            ->ordinal(2)
                                            ->priceMoney(
                                                MoneyBuilder::init()
                                                    ->amount(225)
                                                    ->currency('USD')
                                                    ->build()
                                            )
                                            ->pricingType('FIXED_PRICING')
                                            ->build()
                                    )
                                    ->presentAtAllLocations(true)
                                    ->updatedAt('2017-10-26T15:27:31.626Z')
                                    ->version(1509031651626)
                                    ->build()
                            ]
                        )
                        ->build()
                )
                ->presentAtAllLocations(true)
                ->updatedAt('2017-10-26T15:41:32.337Z')
                ->version(1509032492337)
                ->build(),
            CatalogObjectBuilder::init(
                'NNNEM3LA656Q46NXLWCNI7S5',
                'ITEM'
            )
                ->absentAtLocationIds(
                    [
                        'absent_at_location_ids7',
                        'absent_at_location_ids8',
                        'absent_at_location_ids9'
                    ]
                )
                ->catalogV1Ids(
                    [
                        CatalogV1IdBuilder::init()
                            ->catalogV1Id('catalog_v1_id4')
                            ->locationId('location_id4')
                            ->build(),
                        CatalogV1IdBuilder::init()
                            ->catalogV1Id('catalog_v1_id4')
                            ->locationId('location_id4')
                            ->build(),
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
                ->itemData(
                    CatalogItemBuilder::init()
                        ->categoryId('E7CLE5RZZ744BHWVQQEAHI2C')
                        ->description('Relaxing green herbal tea.')
                        ->name('Tea - Green')
                        ->productType('REGULAR')
                        ->taxIds(
                            [
                                'ZXITPM6RWHZ7GZ7EIP3YKECM'
                            ]
                        )
                        ->variations(
                            [
                                CatalogObjectBuilder::init(
                                    'FHYBVIA6NVBCSOVETA62WEA4',
                                    'ITEM_VARIATION'
                                )
                                    ->isDeleted(false)
                                    ->itemVariationData(
                                        CatalogItemVariationBuilder::init()
                                            ->itemId('NNNEM3LA656Q46NXLWCNI7S5')
                                            ->name('Regular')
                                            ->ordinal(1)
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
                                    ->updatedAt('2017-10-26T15:29:00.524Z')
                                    ->version(1509031740524)
                                    ->build()
                            ]
                        )
                        ->build()
                )
                ->presentAtAllLocations(true)
                ->updatedAt('2017-10-26T15:41:23.232Z')
                ->version(1509032483232)
                ->build()
        ]
    )
    ->relatedObjects(
        [
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
                ->build(),
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
                ->build()
        ]
    )
    ->build();
```

