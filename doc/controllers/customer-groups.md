# Customer Groups

```php
$customerGroupsController = $client->getCustomerGroupsController();
```

## Class Name

`CustomerGroupsController`

## Methods

* [List Customer Groups](../../doc/controllers/customer-groups.md#list-customer-groups)
* [Create Customer Group](../../doc/controllers/customer-groups.md#create-customer-group)
* [Delete Customer Group](../../doc/controllers/customer-groups.md#delete-customer-group)
* [Retrieve Customer Group](../../doc/controllers/customer-groups.md#retrieve-customer-group)
* [Update Customer Group](../../doc/controllers/customer-groups.md#update-customer-group)


# List Customer Groups

Retrieves the list of customer groups of a business.

```php
function listCustomerGroups(?string $cursor = null, ?int $limit = null): ListCustomerGroupsResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `cursor` | `?string` | Query, Optional | A pagination cursor returned by a previous call to this endpoint.<br>Provide this cursor to retrieve the next set of results for your original query.<br><br>For more information, see [Pagination](https://developer.squareup.com/docs/working-with-apis/pagination). |
| `limit` | `?int` | Query, Optional | The maximum number of results to return in a single page. This limit is advisory. The response might contain more or fewer results.<br>The limit is ignored if it is less than 1 or greater than 50. The default value is 50.<br><br>For more information, see [Pagination](https://developer.squareup.com/docs/working-with-apis/pagination). |

## Requires scope

### oauth2

`CUSTOMERS_READ`

## Response Type

**200**: Success

[`ListCustomerGroupsResponse`](../../doc/models/list-customer-groups-response.md)

## Example Usage

```php
$customerGroupsController = $client->getCustomerGroupsController();

try {
    $result = $customerGroupsController->listCustomerGroups();
    echo 'ListCustomerGroupsResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Create Customer Group

Creates a new customer group for a business.

The request must include the `name` value of the group.

```php
function createCustomerGroup(CreateCustomerGroupRequest $body): CreateCustomerGroupResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`CreateCustomerGroupRequest`](../../doc/models/create-customer-group-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`CUSTOMERS_WRITE`

## Response Type

**200**: Success

[`CreateCustomerGroupResponse`](../../doc/models/create-customer-group-response.md)

## Example Usage

```php
$body = CreateCustomerGroupRequestBuilder::init(
    CustomerGroupBuilder::init(
        'name8'
    )->build()
)->build();

$customerGroupsController = $client->getCustomerGroupsController();

try {
    $result = $customerGroupsController->createCustomerGroup($body);
    echo 'CreateCustomerGroupResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Delete Customer Group

Deletes a customer group as identified by the `group_id` value.

```php
function deleteCustomerGroup(string $groupId): DeleteCustomerGroupResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `groupId` | `string` | Template, Required | The ID of the customer group to delete. |

## Requires scope

### oauth2

`CUSTOMERS_WRITE`

## Response Type

**200**: Success

[`DeleteCustomerGroupResponse`](../../doc/models/delete-customer-group-response.md)

## Example Usage

```php
$groupId = 'group_id0';

$customerGroupsController = $client->getCustomerGroupsController();

try {
    $result = $customerGroupsController->deleteCustomerGroup($groupId);
    echo 'DeleteCustomerGroupResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Retrieve Customer Group

Retrieves a specific customer group as identified by the `group_id` value.

```php
function retrieveCustomerGroup(string $groupId): RetrieveCustomerGroupResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `groupId` | `string` | Template, Required | The ID of the customer group to retrieve. |

## Requires scope

### oauth2

`CUSTOMERS_READ`

## Response Type

**200**: Success

[`RetrieveCustomerGroupResponse`](../../doc/models/retrieve-customer-group-response.md)

## Example Usage

```php
$groupId = 'group_id0';

$customerGroupsController = $client->getCustomerGroupsController();

try {
    $result = $customerGroupsController->retrieveCustomerGroup($groupId);
    echo 'RetrieveCustomerGroupResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Update Customer Group

Updates a customer group as identified by the `group_id` value.

```php
function updateCustomerGroup(string $groupId, UpdateCustomerGroupRequest $body): UpdateCustomerGroupResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `groupId` | `string` | Template, Required | The ID of the customer group to update. |
| `body` | [`UpdateCustomerGroupRequest`](../../doc/models/update-customer-group-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`CUSTOMERS_READ`, `CUSTOMERS_WRITE`

## Response Type

**200**: Success

[`UpdateCustomerGroupResponse`](../../doc/models/update-customer-group-response.md)

## Example Usage

```php
$groupId = 'group_id0';

$body = UpdateCustomerGroupRequestBuilder::init(
    CustomerGroupBuilder::init(
        'name8'
    )->build()
)->build();

$customerGroupsController = $client->getCustomerGroupsController();

try {
    $result = $customerGroupsController->updateCustomerGroup(
        $groupId,
        $body
    );
    echo 'UpdateCustomerGroupResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

