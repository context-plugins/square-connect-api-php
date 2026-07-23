
# Catalog Item Option

A group of variations for a `CatalogItem`.

## Structure

`CatalogItemOption`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `description` | `?string` | Optional | The item option's human-readable description. Displayed in the Square<br>Point of Sale app for the seller and in the Online Store or on receipts for<br>the buyer. This is a searchable attribute for use in applicable query filters. | getDescription(): ?string | setDescription(?string description): void |
| `displayName` | `?string` | Optional | The item option's display name for the customer. This is a searchable attribute for use in applicable query filters. | getDisplayName(): ?string | setDisplayName(?string displayName): void |
| `name` | `?string` | Optional | The item option's display name for the seller. Must be unique across<br>all item options. This is a searchable attribute for use in applicable query filters. | getName(): ?string | setName(?string name): void |
| `showColors` | `?bool` | Optional | If true, display colors for entries in `values` when present. | getShowColors(): ?bool | setShowColors(?bool showColors): void |
| `values` | [`?(CatalogObject[])`](../../doc/models/catalog-object.md) | Optional | A list of CatalogObjects containing the<br>`CatalogItemOptionValue`s for this item. | getValues(): ?array | setValues(?array values): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CatalogItemOptionBuilder;
use SquareConnectAPILib\Models\Builders\CatalogObjectBuilder;
use SquareConnectAPILib\Models\Builders\CatalogV1IdBuilder;
use SquareConnectAPILib\Models\Builders\CatalogCustomAttributeDefinitionBuilder;
use SquareConnectAPILib\Models\Builders\CatalogCustomAttributeDefinitionNumberConfigBuilder;
use SquareConnectAPILib\Models\Builders\CatalogCustomAttributeValueBuilder;

$catalogItemOption = CatalogItemOptionBuilder::init()
    ->description('description8')
    ->displayName('display_name8')
    ->name('name8')
    ->showColors(false)
    ->values(
        [
            CatalogObjectBuilder::init(
                'id0',
                'type0'
            )
                ->absentAtLocationIds(
                    [
                        'absent_at_location_ids1'
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
                            ->build(),
                        'key2' => CatalogCustomAttributeValueBuilder::init()
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
                'id0',
                'type0'
            )
                ->absentAtLocationIds(
                    [
                        'absent_at_location_ids1'
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
                            ->build(),
                        'key2' => CatalogCustomAttributeValueBuilder::init()
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

