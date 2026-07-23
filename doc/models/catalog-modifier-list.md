
# Catalog Modifier List

A list of modifiers applicable to items at the time of sale.

For example, a "Condiments" modifier list applicable to a "Hot Dog" item
may contain "Ketchup", "Mustard", and "Relish" modifiers.
Use the `selection_type` field to specify whether or not multiple selections from
the modifier list are allowed.

## Structure

`CatalogModifierList`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `modifiers` | [`?(CatalogObject[])`](../../doc/models/catalog-object.md) | Optional | The options included in the `CatalogModifierList`.<br>You must include at least one `CatalogModifier`.<br>Each CatalogObject must have type `MODIFIER` and contain<br>`CatalogModifier` data. | getModifiers(): ?array | setModifiers(?array modifiers): void |
| `name` | `?string` | Optional | The name for the `CatalogModifierList` instance. This is a searchable attribute for use in applicable query filters, and its value length is of Unicode code points.<br><br>**Constraints**: *Maximum Length*: `255` | getName(): ?string | setName(?string name): void |
| `ordinal` | `?int` | Optional | Determines where this modifier list appears in a list of `CatalogModifierList` values. | getOrdinal(): ?int | setOrdinal(?int ordinal): void |
| `selectionType` | `?string` | Optional | Indicates whether multiple options from the modifier list<br>can be applied to a single `CatalogItem`. | getSelectionType(): ?string | setSelectionType(?string selectionType): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CatalogModifierListBuilder;
use SquareConnectAPILib\Models\Builders\CatalogObjectBuilder;
use SquareConnectAPILib\Models\Builders\CatalogV1IdBuilder;
use SquareConnectAPILib\Models\Builders\CatalogCustomAttributeDefinitionBuilder;
use SquareConnectAPILib\Models\Builders\CatalogCustomAttributeDefinitionNumberConfigBuilder;
use SquareConnectAPILib\Models\Builders\CatalogCustomAttributeValueBuilder;

$catalogModifierList = CatalogModifierListBuilder::init()
    ->modifiers(
        [
            CatalogObjectBuilder::init(
                'id4',
                'type6'
            )
                ->absentAtLocationIds(
                    [
                        'absent_at_location_ids5',
                        'absent_at_location_ids6',
                        'absent_at_location_ids7'
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
    ->name('name6')
    ->ordinal(236)
    ->selectionType('selection_type4')
    ->build();
```

