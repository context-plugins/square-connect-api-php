
# List Catalog Response

## Structure

`ListCatalogResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cursor` | `?string` | Optional | The pagination cursor to be used in a subsequent request. If unset, this is the final response.<br>See [Pagination](https://developer.squareup.com/docs/basics/api101/pagination) for more information. | getCursor(): ?string | setCursor(?string cursor): void |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `objects` | [`?(CatalogObject[])`](../../doc/models/catalog-object.md) | Optional | The CatalogObjects returned. | getObjects(): ?array | setObjects(?array objects): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\ListCatalogResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\CatalogObjectBuilder;
use SquareConnectAPILib\Models\Builders\CatalogV1IdBuilder;
use SquareConnectAPILib\Models\Builders\CatalogCategoryBuilder;
use SquareConnectAPILib\Models\Builders\CatalogCustomAttributeDefinitionBuilder;
use SquareConnectAPILib\Models\Builders\CatalogCustomAttributeDefinitionNumberConfigBuilder;
use SquareConnectAPILib\Models\Builders\CatalogCustomAttributeValueBuilder;
use SquareConnectAPILib\Models\Builders\CatalogTaxBuilder;

$listCatalogResponse = ListCatalogResponseBuilder::init()
    ->cursor('cursor2')
    ->errors(
        [
            ErrorBuilder::init(
                'category8',
                'code8'
            )
                ->detail('detail6')
                ->field('field4')
                ->build()
        ]
    )
    ->objects(
        [
            CatalogObjectBuilder::init(
                '5ZYQZZ2IECPVJ2IJ5KQPRDC3',
                'CATEGORY'
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
                ->updatedAt('2017-02-21T14:50:26.495Z')
                ->version(1487688626495)
                ->build(),
            CatalogObjectBuilder::init(
                'L5R47DGBZOOVKCAFIXC56AEN',
                'TAX'
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
                ->updatedAt('2017-02-21T14:50:26.495Z')
                ->version(1487688626495)
                ->build()
        ]
    )
    ->build();
```

