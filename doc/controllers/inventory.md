# Inventory

```php
$inventoryController = $client->getInventoryController();
```

## Class Name

`InventoryController`

## Methods

* [Deprecated Retrieve Inventory Adjustment](../../doc/controllers/inventory.md#deprecated-retrieve-inventory-adjustment)
* [Retrieve Inventory Adjustment](../../doc/controllers/inventory.md#retrieve-inventory-adjustment)
* [Deprecated Batch Change Inventory](../../doc/controllers/inventory.md#deprecated-batch-change-inventory)
* [Deprecated Batch Retrieve Inventory Changes](../../doc/controllers/inventory.md#deprecated-batch-retrieve-inventory-changes)
* [Deprecated Batch Retrieve Inventory Counts](../../doc/controllers/inventory.md#deprecated-batch-retrieve-inventory-counts)
* [Batch Change Inventory](../../doc/controllers/inventory.md#batch-change-inventory)
* [Batch Retrieve Inventory Changes](../../doc/controllers/inventory.md#batch-retrieve-inventory-changes)
* [Batch Retrieve Inventory Counts](../../doc/controllers/inventory.md#batch-retrieve-inventory-counts)
* [Deprecated Retrieve Inventory Physical Count](../../doc/controllers/inventory.md#deprecated-retrieve-inventory-physical-count)
* [Retrieve Inventory Physical Count](../../doc/controllers/inventory.md#retrieve-inventory-physical-count)
* [Retrieve Inventory Transfer](../../doc/controllers/inventory.md#retrieve-inventory-transfer)
* [Retrieve Inventory Count](../../doc/controllers/inventory.md#retrieve-inventory-count)
* [Retrieve Inventory Changes](../../doc/controllers/inventory.md#retrieve-inventory-changes)


# Deprecated Retrieve Inventory Adjustment

Deprecated version of [RetrieveInventoryAdjustment](https://developer.squareup.com/reference/square_2021-08-18/inventory-api/retrieve-inventory-adjustment) after the endpoint URL
is updated to conform to the standard convention.

```php
function deprecatedRetrieveInventoryAdjustment(string $adjustmentId): RetrieveInventoryAdjustmentResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `adjustmentId` | `string` | Template, Required | ID of the [InventoryAdjustment](https://developer.squareup.com/reference/square_2021-08-18/objects/InventoryAdjustment) to retrieve. |

## Requires scope

### oauth2

`INVENTORY_READ`

## Response Type

**200**: Success

[`RetrieveInventoryAdjustmentResponse`](../../doc/models/retrieve-inventory-adjustment-response.md)

## Example Usage

```php
$adjustmentId = 'adjustment_id0';

$inventoryController = $client->getInventoryController();

try {
    $result = $inventoryController->deprecatedRetrieveInventoryAdjustment($adjustmentId);
    echo 'RetrieveInventoryAdjustmentResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Retrieve Inventory Adjustment

Returns the [InventoryAdjustment](https://developer.squareup.com/reference/square_2021-08-18/objects/InventoryAdjustment) object
with the provided `adjustment_id`.

```php
function retrieveInventoryAdjustment(string $adjustmentId): RetrieveInventoryAdjustmentResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `adjustmentId` | `string` | Template, Required | ID of the [InventoryAdjustment](https://developer.squareup.com/reference/square_2021-08-18/objects/InventoryAdjustment) to retrieve. |

## Requires scope

### oauth2

`INVENTORY_READ`

## Response Type

**200**: Success

[`RetrieveInventoryAdjustmentResponse`](../../doc/models/retrieve-inventory-adjustment-response.md)

## Example Usage

```php
$adjustmentId = 'adjustment_id0';

$inventoryController = $client->getInventoryController();

try {
    $result = $inventoryController->retrieveInventoryAdjustment($adjustmentId);
    echo 'RetrieveInventoryAdjustmentResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Deprecated Batch Change Inventory

Deprecated version of [BatchChangeInventory](https://developer.squareup.com/reference/square_2021-08-18/inventory-api/batch-change-inventory) after the endpoint URL
is updated to conform to the standard convention.

```php
function deprecatedBatchChangeInventory(BatchChangeInventoryRequest $body): BatchChangeInventoryResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`BatchChangeInventoryRequest`](../../doc/models/batch-change-inventory-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`INVENTORY_WRITE`

## Response Type

**200**: Success

[`BatchChangeInventoryResponse`](../../doc/models/batch-change-inventory-response.md)

## Example Usage

```php
$body = BatchChangeInventoryRequestBuilder::init(
    'idempotency_key2'
)->build();

$inventoryController = $client->getInventoryController();

try {
    $result = $inventoryController->deprecatedBatchChangeInventory($body);
    echo 'BatchChangeInventoryResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Deprecated Batch Retrieve Inventory Changes

Deprecated version of [BatchRetrieveInventoryChanges](https://developer.squareup.com/reference/square_2021-08-18/inventory-api/batch-retrieve-inventory-changes) after the endpoint URL
is updated to conform to the standard convention.

```php
function deprecatedBatchRetrieveInventoryChanges(
    BatchRetrieveInventoryChangesRequest $body
): BatchRetrieveInventoryChangesResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`BatchRetrieveInventoryChangesRequest`](../../doc/models/batch-retrieve-inventory-changes-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`INVENTORY_READ`

## Response Type

**200**: Success

[`BatchRetrieveInventoryChangesResponse`](../../doc/models/batch-retrieve-inventory-changes-response.md)

## Example Usage

```php
$body = BatchRetrieveInventoryChangesRequestBuilder::init()->build();

$inventoryController = $client->getInventoryController();

try {
    $result = $inventoryController->deprecatedBatchRetrieveInventoryChanges($body);
    echo 'BatchRetrieveInventoryChangesResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Deprecated Batch Retrieve Inventory Counts

Deprecated version of [BatchRetrieveInventoryCounts](https://developer.squareup.com/reference/square_2021-08-18/inventory-api/batch-retrieve-inventory-counts) after the endpoint URL
is updated to conform to the standard convention.

```php
function deprecatedBatchRetrieveInventoryCounts(
    BatchRetrieveInventoryCountsRequest $body
): BatchRetrieveInventoryCountsResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`BatchRetrieveInventoryCountsRequest`](../../doc/models/batch-retrieve-inventory-counts-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`INVENTORY_READ`

## Response Type

**200**: Success

[`BatchRetrieveInventoryCountsResponse`](../../doc/models/batch-retrieve-inventory-counts-response.md)

## Example Usage

```php
$body = BatchRetrieveInventoryCountsRequestBuilder::init()->build();

$inventoryController = $client->getInventoryController();

try {
    $result = $inventoryController->deprecatedBatchRetrieveInventoryCounts($body);
    echo 'BatchRetrieveInventoryCountsResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Batch Change Inventory

Applies adjustments and counts to the provided item quantities.

On success: returns the current calculated counts for all objects
referenced in the request.
On failure: returns a list of related errors.

```php
function batchChangeInventory(BatchChangeInventoryRequest $body): BatchChangeInventoryResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`BatchChangeInventoryRequest`](../../doc/models/batch-change-inventory-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`INVENTORY_WRITE`

## Response Type

**200**: Success

[`BatchChangeInventoryResponse`](../../doc/models/batch-change-inventory-response.md)

## Example Usage

```php
$body = BatchChangeInventoryRequestBuilder::init(
    'idempotency_key2'
)->build();

$inventoryController = $client->getInventoryController();

try {
    $result = $inventoryController->batchChangeInventory($body);
    echo 'BatchChangeInventoryResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Batch Retrieve Inventory Changes

Returns historical physical counts and adjustments based on the
provided filter criteria.

Results are paginated and sorted in ascending order according their
`occurred_at` timestamp (oldest first).

BatchRetrieveInventoryChanges is a catch-all query endpoint for queries
that cannot be handled by other, simpler endpoints.

```php
function batchRetrieveInventoryChanges(
    BatchRetrieveInventoryChangesRequest $body
): BatchRetrieveInventoryChangesResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`BatchRetrieveInventoryChangesRequest`](../../doc/models/batch-retrieve-inventory-changes-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`INVENTORY_READ`

## Response Type

**200**: Success

[`BatchRetrieveInventoryChangesResponse`](../../doc/models/batch-retrieve-inventory-changes-response.md)

## Example Usage

```php
$body = BatchRetrieveInventoryChangesRequestBuilder::init()->build();

$inventoryController = $client->getInventoryController();

try {
    $result = $inventoryController->batchRetrieveInventoryChanges($body);
    echo 'BatchRetrieveInventoryChangesResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Batch Retrieve Inventory Counts

Returns current counts for the provided
[CatalogObject](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogObject)s at the requested
[Location](https://developer.squareup.com/reference/square_2021-08-18/objects/Location)s.

Results are paginated and sorted in descending order according to their
`calculated_at` timestamp (newest first).

When `updated_after` is specified, only counts that have changed since that
time (based on the server timestamp for the most recent change) are
returned. This allows clients to perform a "sync" operation, for example
in response to receiving a Webhook notification.

```php
function batchRetrieveInventoryCounts(
    BatchRetrieveInventoryCountsRequest $body
): BatchRetrieveInventoryCountsResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`BatchRetrieveInventoryCountsRequest`](../../doc/models/batch-retrieve-inventory-counts-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`INVENTORY_READ`

## Response Type

**200**: Success

[`BatchRetrieveInventoryCountsResponse`](../../doc/models/batch-retrieve-inventory-counts-response.md)

## Example Usage

```php
$body = BatchRetrieveInventoryCountsRequestBuilder::init()->build();

$inventoryController = $client->getInventoryController();

try {
    $result = $inventoryController->batchRetrieveInventoryCounts($body);
    echo 'BatchRetrieveInventoryCountsResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Deprecated Retrieve Inventory Physical Count

Deprecated version of [RetrieveInventoryPhysicalCount](https://developer.squareup.com/reference/square_2021-08-18/inventory-api/retrieve-inventory-physical-count) after the endpoint URL
is updated to conform to the standard convention.

```php
function deprecatedRetrieveInventoryPhysicalCount(
    string $physicalCountId
): RetrieveInventoryPhysicalCountResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `physicalCountId` | `string` | Template, Required | ID of the<br>[InventoryPhysicalCount](https://developer.squareup.com/reference/square_2021-08-18/objects/InventoryPhysicalCount) to retrieve. |

## Requires scope

### oauth2

`INVENTORY_READ`

## Response Type

**200**: Success

[`RetrieveInventoryPhysicalCountResponse`](../../doc/models/retrieve-inventory-physical-count-response.md)

## Example Usage

```php
$physicalCountId = 'physical_count_id2';

$inventoryController = $client->getInventoryController();

try {
    $result = $inventoryController->deprecatedRetrieveInventoryPhysicalCount($physicalCountId);
    echo 'RetrieveInventoryPhysicalCountResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Retrieve Inventory Physical Count

Returns the [InventoryPhysicalCount](https://developer.squareup.com/reference/square_2021-08-18/objects/InventoryPhysicalCount)
object with the provided `physical_count_id`.

```php
function retrieveInventoryPhysicalCount(string $physicalCountId): RetrieveInventoryPhysicalCountResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `physicalCountId` | `string` | Template, Required | ID of the<br>[InventoryPhysicalCount](https://developer.squareup.com/reference/square_2021-08-18/objects/InventoryPhysicalCount) to retrieve. |

## Requires scope

### oauth2

`INVENTORY_READ`

## Response Type

**200**: Success

[`RetrieveInventoryPhysicalCountResponse`](../../doc/models/retrieve-inventory-physical-count-response.md)

## Example Usage

```php
$physicalCountId = 'physical_count_id2';

$inventoryController = $client->getInventoryController();

try {
    $result = $inventoryController->retrieveInventoryPhysicalCount($physicalCountId);
    echo 'RetrieveInventoryPhysicalCountResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Retrieve Inventory Transfer

Returns the [InventoryTransfer](https://developer.squareup.com/reference/square_2021-08-18/objects/InventoryTransfer) object
with the provided `transfer_id`.

```php
function retrieveInventoryTransfer(string $transferId): RetrieveInventoryTransferResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `transferId` | `string` | Template, Required | ID of the [InventoryTransfer](https://developer.squareup.com/reference/square_2021-08-18/objects/InventoryTransfer) to retrieve. |

## Requires scope

### oauth2

`INVENTORY_READ`

## Response Type

**200**: Success

[`RetrieveInventoryTransferResponse`](../../doc/models/retrieve-inventory-transfer-response.md)

## Example Usage

```php
$transferId = 'transfer_id6';

$inventoryController = $client->getInventoryController();

try {
    $result = $inventoryController->retrieveInventoryTransfer($transferId);
    echo 'RetrieveInventoryTransferResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Retrieve Inventory Count

Retrieves the current calculated stock count for a given
[CatalogObject](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogObject) at a given set of
[Location](https://developer.squareup.com/reference/square_2021-08-18/objects/Location)s. Responses are paginated and unsorted.
For more sophisticated queries, use a batch endpoint.

```php
function retrieveInventoryCount(
    string $catalogObjectId,
    ?string $locationIds = null,
    ?string $cursor = null
): RetrieveInventoryCountResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `catalogObjectId` | `string` | Template, Required | ID of the [CatalogObject](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogObject) to retrieve. |
| `locationIds` | `?string` | Query, Optional | The [Location](https://developer.squareup.com/reference/square_2021-08-18/objects/Location) IDs to look up as a comma-separated<br>list. An empty list queries all locations. |
| `cursor` | `?string` | Query, Optional | A pagination cursor returned by a previous call to this endpoint.<br>Provide this to retrieve the next set of results for the original query.<br><br>See the [Pagination](https://developer.squareup.com/docs/working-with-apis/pagination) guide for more information. |

## Requires scope

### oauth2

`INVENTORY_READ`

## Response Type

**200**: Success

[`RetrieveInventoryCountResponse`](../../doc/models/retrieve-inventory-count-response.md)

## Example Usage

```php
$catalogObjectId = 'catalog_object_id6';

$inventoryController = $client->getInventoryController();

try {
    $result = $inventoryController->retrieveInventoryCount($catalogObjectId);
    echo 'RetrieveInventoryCountResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Retrieve Inventory Changes

Returns a set of physical counts and inventory adjustments for the
provided [CatalogObject](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogObject) at the requested
[Location](https://developer.squareup.com/reference/square_2021-08-18/objects/Location)s.

You can achieve the same result by calling [BatchRetrieveInventoryChanges](https://developer.squareup.com/reference/square_2021-08-18/inventory-api/batch-retrieve-inventory-changes)
and having the `catalog_object_ids` list contain a single element of the `CatalogObject` ID.

Results are paginated and sorted in descending order according to their
`occurred_at` timestamp (newest first).

There are no limits on how far back the caller can page. This endpoint can be
used to display recent changes for a specific item. For more
sophisticated queries, use a batch endpoint.

```php
function retrieveInventoryChanges(
    string $catalogObjectId,
    ?string $locationIds = null,
    ?string $cursor = null
): RetrieveInventoryChangesResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `catalogObjectId` | `string` | Template, Required | ID of the [CatalogObject](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogObject) to retrieve. |
| `locationIds` | `?string` | Query, Optional | The [Location](https://developer.squareup.com/reference/square_2021-08-18/objects/Location) IDs to look up as a comma-separated<br>list. An empty list queries all locations. |
| `cursor` | `?string` | Query, Optional | A pagination cursor returned by a previous call to this endpoint.<br>Provide this to retrieve the next set of results for the original query.<br><br>See the [Pagination](https://developer.squareup.com/docs/working-with-apis/pagination) guide for more information. |

## Requires scope

### oauth2

`INVENTORY_READ`

## Response Type

**200**: Success

[`RetrieveInventoryChangesResponse`](../../doc/models/retrieve-inventory-changes-response.md)

## Example Usage

```php
$catalogObjectId = 'catalog_object_id6';

$inventoryController = $client->getInventoryController();

try {
    $result = $inventoryController->retrieveInventoryChanges($catalogObjectId);
    echo 'RetrieveInventoryChangesResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

