
# Catalog Custom Attribute Definition

Contains information defining a custom attribute. Custom attributes are
intended to store additional information about a catalog object or to associate a
catalog object with an entity in another system. Do not use custom attributes
to store any sensitive information (personally identifiable information, card details, etc.).
[Read more about custom attributes](https://developer.squareup.com/docs/catalog-api/add-custom-attributes)

## Structure

`CatalogCustomAttributeDefinition`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `allowedObjectTypes` | `string[]` | Required | The set of Catalog Object Types that this Custom Attribute may be applied to.<br>Currently, only `ITEM` and `ITEM_VARIATION` are allowed. At least one type must be included. | getAllowedObjectTypes(): array | setAllowedObjectTypes(array allowedObjectTypes): void |
| `appVisibility` | `?string` | Optional | The visibility of a custom attribute to applications other than the application<br>that created the attribute. | getAppVisibility(): ?string | setAppVisibility(?string appVisibility): void |
| `customAttributeUsageCount` | `?int` | Optional | __Read-only.__ The number of custom attributes that reference this<br>custom attribute definition. Set by the server in response to a ListCatalog<br>request with `include_counts` set to `true`.  If the actual count is greater<br>than 100, `custom_attribute_usage_count` will be set to `100`. | getCustomAttributeUsageCount(): ?int | setCustomAttributeUsageCount(?int customAttributeUsageCount): void |
| `description` | `?string` | Optional | Seller-oriented description of the meaning of this Custom Attribute,<br>any constraints that the seller should observe, etc. May be displayed as a tooltip in Square UIs.<br><br>**Constraints**: *Maximum Length*: `255` | getDescription(): ?string | setDescription(?string description): void |
| `key` | `?string` | Optional | The name of the desired custom attribute key that can be used to access<br>the custom attribute value on catalog objects. Cannot be modified after the<br>custom attribute definition has been created.<br>Must be between 1 and 60 characters, and may only contain the characters `[a-zA-Z0-9_-]`.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `60`, *Pattern*: `^[a-zA-Z0-9_-]*$` | getKey(): ?string | setKey(?string key): void |
| `name` | `string` | Required | The name of this definition for API and seller-facing UI purposes.<br>The name must be unique within the (merchant, application) pair. Required.<br>May not be empty and may not exceed 255 characters. Can be modified after creation.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `255` | getName(): string | setName(string name): void |
| `numberConfig` | [`?CatalogCustomAttributeDefinitionNumberConfig`](../../doc/models/catalog-custom-attribute-definition-number-config.md) | Optional | - | getNumberConfig(): ?CatalogCustomAttributeDefinitionNumberConfig | setNumberConfig(?CatalogCustomAttributeDefinitionNumberConfig numberConfig): void |
| `selectionConfig` | [`?CatalogCustomAttributeDefinitionSelectionConfig`](../../doc/models/catalog-custom-attribute-definition-selection-config.md) | Optional | Configuration associated with `SELECTION`-type custom attribute definitions. | getSelectionConfig(): ?CatalogCustomAttributeDefinitionSelectionConfig | setSelectionConfig(?CatalogCustomAttributeDefinitionSelectionConfig selectionConfig): void |
| `sellerVisibility` | `?string` | Optional | The visibility of a custom attribute in seller-facing UIs (including Square Point<br>of Sale applications and Square Dashboard). May be modified. | getSellerVisibility(): ?string | setSellerVisibility(?string sellerVisibility): void |
| `sourceApplication` | [`?SourceApplication`](../../doc/models/source-application.md) | Optional | Provides information about the application used to generate a change. | getSourceApplication(): ?SourceApplication | setSourceApplication(?SourceApplication sourceApplication): void |
| `stringConfig` | [`?CatalogCustomAttributeDefinitionStringConfig`](../../doc/models/catalog-custom-attribute-definition-string-config.md) | Optional | Configuration associated with Custom Attribute Definitions of type `STRING`. | getStringConfig(): ?CatalogCustomAttributeDefinitionStringConfig | setStringConfig(?CatalogCustomAttributeDefinitionStringConfig stringConfig): void |
| `type` | `string` | Required | The type of this custom attribute. Cannot be modified after creation.<br>Required. | getType(): string | setType(string type): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CatalogCustomAttributeDefinitionBuilder;
use SquareConnectAPILib\Models\Builders\CatalogCustomAttributeDefinitionNumberConfigBuilder;

$catalogCustomAttributeDefinition = CatalogCustomAttributeDefinitionBuilder::init(
    [
        'allowed_object_types0'
    ],
    'name0',
    'type0'
)
    ->appVisibility('app_visibility0')
    ->customAttributeUsageCount(240)
    ->description('description0')
    ->key('key0')
    ->numberConfig(
        CatalogCustomAttributeDefinitionNumberConfigBuilder::init()
            ->precision(5)
            ->build()
    )
    ->build();
```

