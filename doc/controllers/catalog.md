# Catalog

```php
$catalogController = $client->getCatalogController();
```

## Class Name

`CatalogController`

## Methods

* [Batch Delete Catalog Objects](../../doc/controllers/catalog.md#batch-delete-catalog-objects)
* [Batch Retrieve Catalog Objects](../../doc/controllers/catalog.md#batch-retrieve-catalog-objects)
* [Batch Upsert Catalog Objects](../../doc/controllers/catalog.md#batch-upsert-catalog-objects)
* [Catalog Info](../../doc/controllers/catalog.md#catalog-info)
* [List Catalog](../../doc/controllers/catalog.md#list-catalog)
* [Upsert Catalog Object](../../doc/controllers/catalog.md#upsert-catalog-object)
* [Delete Catalog Object](../../doc/controllers/catalog.md#delete-catalog-object)
* [Retrieve Catalog Object](../../doc/controllers/catalog.md#retrieve-catalog-object)
* [Search Catalog Objects](../../doc/controllers/catalog.md#search-catalog-objects)
* [Search Catalog Items](../../doc/controllers/catalog.md#search-catalog-items)
* [Update Item Modifier Lists](../../doc/controllers/catalog.md#update-item-modifier-lists)
* [Update Item Taxes](../../doc/controllers/catalog.md#update-item-taxes)


# Batch Delete Catalog Objects

Deletes a set of [CatalogItem](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogItem)s based on the
provided list of target IDs and returns a set of successfully deleted IDs in
the response. Deletion is a cascading event such that all children of the
targeted object are also deleted. For example, deleting a CatalogItem will
also delete all of its [CatalogItemVariation](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogItemVariation)
children.

`BatchDeleteCatalogObjects` succeeds even if only a portion of the targeted
IDs can be deleted. The response will only include IDs that were
actually deleted.

```php
function batchDeleteCatalogObjects(BatchDeleteCatalogObjectsRequest $body): BatchDeleteCatalogObjectsResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`BatchDeleteCatalogObjectsRequest`](../../doc/models/batch-delete-catalog-objects-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`ITEMS_WRITE`

## Response Type

**200**: Success

[`BatchDeleteCatalogObjectsResponse`](../../doc/models/batch-delete-catalog-objects-response.md)

## Example Usage

```php
$body = BatchDeleteCatalogObjectsRequestBuilder::init()->build();

$catalogController = $client->getCatalogController();

try {
    $result = $catalogController->batchDeleteCatalogObjects($body);
    echo 'BatchDeleteCatalogObjectsResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Batch Retrieve Catalog Objects

Returns a set of objects based on the provided ID.
Each [CatalogItem](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogItem) returned in the set includes all of its
child information including: all of its
[CatalogItemVariation](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogItemVariation) objects, references to
its [CatalogModifierList](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogModifierList) objects, and the ids of
any [CatalogTax](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogTax) objects that apply to it.

```php
function batchRetrieveCatalogObjects(
    BatchRetrieveCatalogObjectsRequest $body
): BatchRetrieveCatalogObjectsResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`BatchRetrieveCatalogObjectsRequest`](../../doc/models/batch-retrieve-catalog-objects-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`ITEMS_READ`

## Response Type

**200**: Success

[`BatchRetrieveCatalogObjectsResponse`](../../doc/models/batch-retrieve-catalog-objects-response.md)

## Example Usage

```php
$body = BatchRetrieveCatalogObjectsRequestBuilder::init(
    [
        'object_ids0',
        'object_ids1',
        'object_ids2'
    ]
)->build();

$catalogController = $client->getCatalogController();

try {
    $result = $catalogController->batchRetrieveCatalogObjects($body);
    echo 'BatchRetrieveCatalogObjectsResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Batch Upsert Catalog Objects

Creates or updates up to 10,000 target objects based on the provided
list of objects. The target objects are grouped into batches and each batch is
inserted/updated in an all-or-nothing manner. If an object within a batch is
malformed in some way, or violates a database constraint, the entire batch
containing that item will be disregarded. However, other batches in the same
request may still succeed. Each batch may contain up to 1,000 objects, and
batches will be processed in order as long as the total object count for the
request (items, variations, modifier lists, discounts, and taxes) is no more
than 10,000.

```php
function batchUpsertCatalogObjects(BatchUpsertCatalogObjectsRequest $body): BatchUpsertCatalogObjectsResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`BatchUpsertCatalogObjectsRequest`](../../doc/models/batch-upsert-catalog-objects-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`ITEMS_WRITE`

## Response Type

**200**: Success

[`BatchUpsertCatalogObjectsResponse`](../../doc/models/batch-upsert-catalog-objects-response.md)

## Example Usage

```php
$body = BatchUpsertCatalogObjectsRequestBuilder::init(
    [
        CatalogObjectBatchBuilder::init(
            [
                CatalogObjectBuilder::init(
                    'id6',
                    'type6'
                )
                    ->categoryData(
                        CatalogCategoryBuilder::init()->build()
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
    'idempotency_key2'
)->build();

$catalogController = $client->getCatalogController();

try {
    $result = $catalogController->batchUpsertCatalogObjects($body);
    echo 'BatchUpsertCatalogObjectsResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Catalog Info

Retrieves information about the Square Catalog API, such as batch size
limits that can be used by the `BatchUpsertCatalogObjects` endpoint.

```php
function catalogInfo(): CatalogInfoResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Requires scope

### oauth2

`ITEMS_READ`

## Response Type

**200**: Success

[`CatalogInfoResponse`](../../doc/models/catalog-info-response.md)

## Example Usage

```php
$catalogController = $client->getCatalogController();

try {
    $result = $catalogController->catalogInfo();
    echo 'CatalogInfoResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# List Catalog

Returns a list of [CatalogObject](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogObject)s that includes
all objects of a set of desired types (for example, all [CatalogItem](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogItem)
and [CatalogTax](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogTax) objects) in the catalog. The `types` parameter
is specified as a comma-separated list of valid [CatalogObject](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogObject) types:
`ITEM`, `ITEM_VARIATION`, `MODIFIER`, `MODIFIER_LIST`, `CATEGORY`, `DISCOUNT`, `TAX`, `IMAGE`.

__Important:__ ListCatalog does not return deleted catalog items. To retrieve
deleted catalog items, use [SearchCatalogObjects](https://developer.squareup.com/reference/square_2021-08-18/catalog-api/search-catalog-objects)
and set the `include_deleted_objects` attribute value to `true`.

```php
function listCatalog(
    ?string $cursor = null,
    ?string $types = null,
    ?int $catalogVersion = null
): ListCatalogResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `cursor` | `?string` | Query, Optional | The pagination cursor returned in the previous response. Leave unset for an initial request.<br>The page size is currently set to be 100.<br>See [Pagination](https://developer.squareup.com/docs/basics/api101/pagination) for more information. |
| `types` | `?string` | Query, Optional | An optional case-insensitive, comma-separated list of object types to retrieve.<br><br>The valid values are defined in the [CatalogObjectType](https://developer.squareup.com/reference/square_2021-08-18/enums/CatalogObjectType) enum, including<br>`ITEM`, `ITEM_VARIATION`, `CATEGORY`, `DISCOUNT`, `TAX`,<br>`MODIFIER`, `MODIFIER_LIST`, or `IMAGE`.<br><br>If this is unspecified, the operation returns objects of all the types at the version of the Square API used to make the request. |
| `catalogVersion` | `?int` | Query, Optional | The specific version of the catalog objects to be included in the response.<br>This allows you to retrieve historical<br>versions of objects. The specified version value is matched against<br>the [CatalogObject](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogObject)s' `version` attribute. |

## Requires scope

### oauth2

`ITEMS_READ`

## Response Type

**200**: Success

[`ListCatalogResponse`](../../doc/models/list-catalog-response.md)

## Example Usage

```php
$catalogController = $client->getCatalogController();

try {
    $result = $catalogController->listCatalog();
    echo 'ListCatalogResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Upsert Catalog Object

Creates or updates the target [CatalogObject](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogObject).

```php
function upsertCatalogObject(UpsertCatalogObjectRequest $body): UpsertCatalogObjectResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`UpsertCatalogObjectRequest`](../../doc/models/upsert-catalog-object-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`ITEMS_WRITE`

## Response Type

**200**: Success

[`UpsertCatalogObjectResponse`](../../doc/models/upsert-catalog-object-response.md)

## Example Usage

```php
$body = UpsertCatalogObjectRequestBuilder::init(
    'idempotency_key2',
    CatalogObjectBuilder::init(
        'id2',
        'type8'
    )
        ->categoryData(
            CatalogCategoryBuilder::init()->build()
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
)->build();

$catalogController = $client->getCatalogController();

try {
    $result = $catalogController->upsertCatalogObject($body);
    echo 'UpsertCatalogObjectResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Delete Catalog Object

Deletes a single [CatalogObject](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogObject) based on the
provided ID and returns the set of successfully deleted IDs in the response.
Deletion is a cascading event such that all children of the targeted object
are also deleted. For example, deleting a [CatalogItem](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogItem)
will also delete all of its
[CatalogItemVariation](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogItemVariation) children.

```php
function deleteCatalogObject(string $objectId): DeleteCatalogObjectResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `objectId` | `string` | Template, Required | The ID of the catalog object to be deleted. When an object is deleted, other<br>objects in the graph that depend on that object will be deleted as well (for example, deleting a<br>catalog item will delete its catalog item variations). |

## Requires scope

### oauth2

`ITEMS_WRITE`

## Response Type

**200**: Success

[`DeleteCatalogObjectResponse`](../../doc/models/delete-catalog-object-response.md)

## Example Usage

```php
$objectId = 'object_id8';

$catalogController = $client->getCatalogController();

try {
    $result = $catalogController->deleteCatalogObject($objectId);
    echo 'DeleteCatalogObjectResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Retrieve Catalog Object

Returns a single [CatalogItem](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogItem) as a
[CatalogObject](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogObject) based on the provided ID. The returned
object includes all of the relevant [CatalogItem](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogItem)
information including: [CatalogItemVariation](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogItemVariation)
children, references to its
[CatalogModifierList](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogModifierList) objects, and the ids of
any [CatalogTax](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogTax) objects that apply to it.

```php
function retrieveCatalogObject(
    string $objectId,
    ?bool $includeRelatedObjects = null,
    ?int $catalogVersion = null
): RetrieveCatalogObjectResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `objectId` | `string` | Template, Required | The object ID of any type of catalog objects to be retrieved. |
| `includeRelatedObjects` | `?bool` | Query, Optional | If `true`, the response will include additional objects that are related to the<br>requested object, as follows:<br><br>If the `object` field of the response contains a `CatalogItem`, its associated<br>`CatalogCategory`, `CatalogTax`, `CatalogImage` and `CatalogModifierList` objects will<br>be returned in the `related_objects` field of the response. If the `object` field of<br>the response contains a `CatalogItemVariation`, its parent `CatalogItem` will be returned<br>in the `related_objects` field of the response.<br><br>Default value: `false` |
| `catalogVersion` | `?int` | Query, Optional | Requests objects as of a specific version of the catalog. This allows you to retrieve historical<br>versions of objects. The value to retrieve a specific version of an object can be found<br>in the version field of [CatalogObject](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogObject)s. |

## Requires scope

### oauth2

`ITEMS_READ`

## Response Type

**200**: Success

[`RetrieveCatalogObjectResponse`](../../doc/models/retrieve-catalog-object-response.md)

## Example Usage

```php
$objectId = 'object_id8';

$catalogController = $client->getCatalogController();

try {
    $result = $catalogController->retrieveCatalogObject($objectId);
    echo 'RetrieveCatalogObjectResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Search Catalog Objects

Searches for [CatalogObject](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogObject) of any type by matching supported search attribute values,
excluding custom attribute values on items or item variations, against one or more of the specified query expressions.

This (`SearchCatalogObjects`) endpoint differs from the [SearchCatalogItems](https://developer.squareup.com/reference/square_2021-08-18/catalog-api/search-catalog-items)
endpoint in the following aspects:

- `SearchCatalogItems` can only search for items or item variations, whereas `SearchCatalogObjects` can search for any type of catalog objects.
- `SearchCatalogItems` supports the custom attribute query filters to return items or item variations that contain custom attribute values, where `SearchCatalogObjects` does not.
- `SearchCatalogItems` does not support the `include_deleted_objects` filter to search for deleted items or item variations, whereas `SearchCatalogObjects` does.
- The both endpoints have different call conventions, including the query filter formats.

```php
function searchCatalogObjects(SearchCatalogObjectsRequest $body): SearchCatalogObjectsResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`SearchCatalogObjectsRequest`](../../doc/models/search-catalog-objects-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`ITEMS_READ`

## Response Type

**200**: Success

[`SearchCatalogObjectsResponse`](../../doc/models/search-catalog-objects-response.md)

## Example Usage

```php
$body = SearchCatalogObjectsRequestBuilder::init()->build();

$catalogController = $client->getCatalogController();

try {
    $result = $catalogController->searchCatalogObjects($body);
    echo 'SearchCatalogObjectsResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Search Catalog Items

Searches for catalog items or item variations by matching supported search attribute values, including
custom attribute values, against one or more of the specified query expressions.

This (`SearchCatalogItems`) endpoint differs from the [SearchCatalogObjects](https://developer.squareup.com/reference/square_2021-08-18/catalog-api/search-catalog-objects)
endpoint in the following aspects:

- `SearchCatalogItems` can only search for items or item variations, whereas `SearchCatalogObjects` can search for any type of catalog objects.
- `SearchCatalogItems` supports the custom attribute query filters to return items or item variations that contain custom attribute values, where `SearchCatalogObjects` does not.
- `SearchCatalogItems` does not support the `include_deleted_objects` filter to search for deleted items or item variations, whereas `SearchCatalogObjects` does.
- The both endpoints use different call conventions, including the query filter formats.

```php
function searchCatalogItems(SearchCatalogItemsRequest $body): SearchCatalogItemsResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`SearchCatalogItemsRequest`](../../doc/models/search-catalog-items-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`ITEMS_READ`

## Response Type

**200**: Success

[`SearchCatalogItemsResponse`](../../doc/models/search-catalog-items-response.md)

## Example Usage

```php
$body = SearchCatalogItemsRequestBuilder::init()->build();

$catalogController = $client->getCatalogController();

try {
    $result = $catalogController->searchCatalogItems($body);
    echo 'SearchCatalogItemsResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Update Item Modifier Lists

Updates the [CatalogModifierList](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogModifierList) objects
that apply to the targeted [CatalogItem](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogItem) without having
to perform an upsert on the entire item.

```php
function updateItemModifierLists(UpdateItemModifierListsRequest $body): UpdateItemModifierListsResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`UpdateItemModifierListsRequest`](../../doc/models/update-item-modifier-lists-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`ITEMS_WRITE`

## Response Type

**200**: Success

[`UpdateItemModifierListsResponse`](../../doc/models/update-item-modifier-lists-response.md)

## Example Usage

```php
$body = UpdateItemModifierListsRequestBuilder::init(
    [
        'item_ids2',
        'item_ids1',
        'item_ids0'
    ]
)->build();

$catalogController = $client->getCatalogController();

try {
    $result = $catalogController->updateItemModifierLists($body);
    echo 'UpdateItemModifierListsResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Update Item Taxes

Updates the [CatalogTax](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogTax) objects that apply to the
targeted [CatalogItem](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogItem) without having to perform an
upsert on the entire item.

```php
function updateItemTaxes(UpdateItemTaxesRequest $body): UpdateItemTaxesResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`UpdateItemTaxesRequest`](../../doc/models/update-item-taxes-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`ITEMS_WRITE`

## Response Type

**200**: Success

[`UpdateItemTaxesResponse`](../../doc/models/update-item-taxes-response.md)

## Example Usage

```php
$body = UpdateItemTaxesRequestBuilder::init(
    [
        'item_ids2',
        'item_ids1',
        'item_ids0'
    ]
)->build();

$catalogController = $client->getCatalogController();

try {
    $result = $catalogController->updateItemTaxes($body);
    echo 'UpdateItemTaxesResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

