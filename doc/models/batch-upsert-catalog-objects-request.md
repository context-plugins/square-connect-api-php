
# Batch Upsert Catalog Objects Request

## Structure

`BatchUpsertCatalogObjectsRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `batches` | [`CatalogObjectBatch[]`](../../doc/models/catalog-object-batch.md) | Required | A batch of CatalogObjects to be inserted/updated atomically.<br>The objects within a batch will be inserted in an all-or-nothing fashion, i.e., if an error occurs<br>attempting to insert or update an object within a batch, the entire batch will be rejected. However, an error<br>in one batch will not affect other batches within the same request.<br><br>For each object, its `updated_at` field is ignored and replaced with a current [timestamp](https://developer.squareup.com/docs/build-basics/working-with-dates), and its<br>`is_deleted` field must not be set to `true`.<br><br>To modify an existing object, supply its ID. To create a new object, use an ID starting<br>with `#`. These IDs may be used to create relationships between an object and attributes of<br>other objects that reference it. For example, you can create a CatalogItem with<br>ID `#ABC` and a CatalogItemVariation with its `item_id` attribute set to<br>`#ABC` in order to associate the CatalogItemVariation with its parent<br>CatalogItem.<br><br>Any `#`-prefixed IDs are valid only within a single atomic batch, and will be replaced by server-generated IDs.<br><br>Each batch may contain up to 1,000 objects. The total number of objects across all batches for a single request<br>may not exceed 10,000. If either of these limits is violated, an error will be returned and no objects will<br>be inserted or updated. | getBatches(): array | setBatches(array batches): void |
| `idempotencyKey` | `string` | Required | A value you specify that uniquely identifies this<br>request among all your requests. A common way to create<br>a valid idempotency key is to use a Universally unique<br>identifier (UUID).<br><br>If you're unsure whether a particular request was successful,<br>you can reattempt it with the same idempotency key without<br>worrying about creating duplicate objects.<br><br>See [Idempotency](https://developer.squareup.com/docs/basics/api101/idempotency) for more information.<br><br>**Constraints**: *Minimum Length*: `1` | getIdempotencyKey(): string | setIdempotencyKey(string idempotencyKey): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\BatchUpsertCatalogObjectsRequestBuilder;
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

$batchUpsertCatalogObjectsRequest = BatchUpsertCatalogObjectsRequestBuilder::init(
    [
        CatalogObjectBatchBuilder::init(
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
        )->build()
    ],
    'idempotency_key0'
)->build();
```

