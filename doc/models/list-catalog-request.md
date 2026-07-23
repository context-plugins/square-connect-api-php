
# List Catalog Request

## Structure

`ListCatalogRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `catalogVersion` | `?int` | Optional | The specific version of the catalog objects to be included in the response.<br>This allows you to retrieve historical<br>versions of objects. The specified version value is matched against<br>the [CatalogObject](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogObject)s' `version` attribute. | getCatalogVersion(): ?int | setCatalogVersion(?int catalogVersion): void |
| `cursor` | `?string` | Optional | The pagination cursor returned in the previous response. Leave unset for an initial request.<br>The page size is currently set to be 100.<br>See [Pagination](https://developer.squareup.com/docs/basics/api101/pagination) for more information. | getCursor(): ?string | setCursor(?string cursor): void |
| `types` | `?string` | Optional | An optional case-insensitive, comma-separated list of object types to retrieve.<br><br>The valid values are defined in the [CatalogObjectType](https://developer.squareup.com/reference/square_2021-08-18/enums/CatalogObjectType) enum, including<br>`ITEM`, `ITEM_VARIATION`, `CATEGORY`, `DISCOUNT`, `TAX`,<br>`MODIFIER`, `MODIFIER_LIST`, or `IMAGE`.<br><br>If this is unspecified, the operation returns objects of all the types at the version of the Square API used to make the request. | getTypes(): ?string | setTypes(?string types): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\ListCatalogRequestBuilder;

$listCatalogRequest = ListCatalogRequestBuilder::init()
    ->catalogVersion(122)
    ->cursor('cursor2')
    ->types('types4')
    ->build();
```

