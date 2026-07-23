
# Catalog Object Batch

A batch of catalog objects.

## Structure

`CatalogObjectBatch`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `objects` | [`CatalogObject[]`](../../doc/models/catalog-object.md) | Required | A list of CatalogObjects belonging to this batch. | getObjects(): array | setObjects(array objects): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CatalogObjectBatchBuilder;
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

$catalogObjectBatch = CatalogObjectBatchBuilder::init(
    [
        CatalogObjectBuilder::init(
            'id6',
            'type6'
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
    ]
)->build();
```

