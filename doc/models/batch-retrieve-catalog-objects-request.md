
# Batch Retrieve Catalog Objects Request

## Structure

`BatchRetrieveCatalogObjectsRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `catalogVersion` | `?int` | Optional | The specific version of the catalog objects to be included in the response.<br>This allows you to retrieve historical versions of objects. The specified version value is matched against<br>the [CatalogObject](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogObject)s' `version` attribute. | getCatalogVersion(): ?int | setCatalogVersion(?int catalogVersion): void |
| `includeRelatedObjects` | `?bool` | Optional | If `true`, the response will include additional objects that are related to the<br>requested objects, as follows:<br><br>If the `objects` field of the response contains a CatalogItem, its associated<br>CatalogCategory objects, CatalogTax objects, CatalogImage objects and<br>CatalogModifierLists will be returned in the `related_objects` field of the<br>response. If the `objects` field of the response contains a CatalogItemVariation,<br>its parent CatalogItem will be returned in the `related_objects` field of<br>the response. | getIncludeRelatedObjects(): ?bool | setIncludeRelatedObjects(?bool includeRelatedObjects): void |
| `objectIds` | `string[]` | Required | The IDs of the CatalogObjects to be retrieved. | getObjectIds(): array | setObjectIds(array objectIds): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\BatchRetrieveCatalogObjectsRequestBuilder;

$batchRetrieveCatalogObjectsRequest = BatchRetrieveCatalogObjectsRequestBuilder::init(
    [
        'object_ids6',
        'object_ids7',
        'object_ids8'
    ]
)
    ->catalogVersion(86)
    ->includeRelatedObjects(false)
    ->build();
```

