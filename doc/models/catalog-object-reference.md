
# Catalog Object Reference

A reference to a Catalog object at a specific version. In general this is
used as an entry point into a graph of catalog objects, where the objects exist
at a specific version.

## Structure

`CatalogObjectReference`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `catalogVersion` | `?int` | Optional | The version of the object. | getCatalogVersion(): ?int | setCatalogVersion(?int catalogVersion): void |
| `objectId` | `?string` | Optional | The ID of the referenced object. | getObjectId(): ?string | setObjectId(?string objectId): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CatalogObjectReferenceBuilder;

$catalogObjectReference = CatalogObjectReferenceBuilder::init()
    ->catalogVersion(240)
    ->objectId('object_id0')
    ->build();
```

