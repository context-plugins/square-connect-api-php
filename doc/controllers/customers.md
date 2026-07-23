# Customers

```php
$customersController = $client->getCustomersController();
```

## Class Name

`CustomersController`

## Methods

* [List Customers](../../doc/controllers/customers.md#list-customers)
* [Create Customer](../../doc/controllers/customers.md#create-customer)
* [Search Customers](../../doc/controllers/customers.md#search-customers)
* [Delete Customer](../../doc/controllers/customers.md#delete-customer)
* [Retrieve Customer](../../doc/controllers/customers.md#retrieve-customer)
* [Update Customer](../../doc/controllers/customers.md#update-customer)
* [Create Customer Card](../../doc/controllers/customers.md#create-customer-card)
* [Delete Customer Card](../../doc/controllers/customers.md#delete-customer-card)
* [Remove Group from Customer](../../doc/controllers/customers.md#remove-group-from-customer)
* [Add Group to Customer](../../doc/controllers/customers.md#add-group-to-customer)


# List Customers

Lists customer profiles associated with a Square account.

Under normal operating conditions, newly created or updated customer profiles become available
for the listing operation in well under 30 seconds. Occasionally, propagation of the new or updated
profiles can take closer to one minute or longer, especially during network incidents and outages.

```php
function listCustomers(
    ?string $cursor = null,
    ?int $limit = null,
    ?string $sortField = null,
    ?string $sortOrder = null
): ListCustomersResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `cursor` | `?string` | Query, Optional | A pagination cursor returned by a previous call to this endpoint.<br>Provide this cursor to retrieve the next set of results for your original query.<br><br>For more information, see [Pagination](https://developer.squareup.com/docs/working-with-apis/pagination). |
| `limit` | `?int` | Query, Optional | The maximum number of results to return in a single page. This limit is advisory. The response might contain more or fewer results.<br>The limit is ignored if it is less than 1 or greater than 100. The default value is 100.<br><br>For more information, see [Pagination](https://developer.squareup.com/docs/working-with-apis/pagination). |
| `sortField` | `?string` | Query, Optional | Indicates how customers should be sorted.<br><br>The default value is `DEFAULT`. |
| `sortOrder` | `?string` | Query, Optional | Indicates whether customers should be sorted in ascending (`ASC`) or<br>descending (`DESC`) order.<br><br>The default value is `ASC`. |

## Requires scope

### oauth2

`CUSTOMERS_READ`

## Response Type

**200**: Success

[`ListCustomersResponse`](../../doc/models/list-customers-response.md)

## Example Usage

```php
$customersController = $client->getCustomersController();

try {
    $result = $customersController->listCustomers();
    echo 'ListCustomersResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Create Customer

Creates a new customer for a business.

You must provide at least one of the following values in your request to this
endpoint:

- `given_name`
- `family_name`
- `company_name`
- `email_address`
- `phone_number`

```php
function createCustomer(CreateCustomerRequest $body): CreateCustomerResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`CreateCustomerRequest`](../../doc/models/create-customer-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`CUSTOMERS_WRITE`

## Response Type

**200**: Success

[`CreateCustomerResponse`](../../doc/models/create-customer-response.md)

## Example Usage

```php
$body = CreateCustomerRequestBuilder::init()->build();

$customersController = $client->getCustomersController();

try {
    $result = $customersController->createCustomer($body);
    echo 'CreateCustomerResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Search Customers

Searches the customer profiles associated with a Square account using a supported query filter.

Calling `SearchCustomers` without any explicit query filter returns all
customer profiles ordered alphabetically based on `given_name` and
`family_name`.

Under normal operating conditions, newly created or updated customer profiles become available
for the search operation in well under 30 seconds. Occasionally, propagation of the new or updated
profiles can take closer to one minute or longer, especially during network incidents and outages.

```php
function searchCustomers(SearchCustomersRequest $body): SearchCustomersResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`SearchCustomersRequest`](../../doc/models/search-customers-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`CUSTOMERS_READ`

## Response Type

**200**: Success

[`SearchCustomersResponse`](../../doc/models/search-customers-response.md)

## Example Usage

```php
$body = SearchCustomersRequestBuilder::init()->build();

$customersController = $client->getCustomersController();

try {
    $result = $customersController->searchCustomers($body);
    echo 'SearchCustomersResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Delete Customer

Deletes a customer profile from a business. This operation also unlinks any associated cards on file.

As a best practice, you should include the `version` field in the request to enable [optimistic concurrency](https://developer.squareup.com/docs/working-with-apis/optimistic-concurrency) control. The value must be set to the current version of the customer profile.

To delete a customer profile that was created by merging existing profiles, you must use the ID of the newly created profile.

```php
function deleteCustomer(string $customerId, ?int $version = null): DeleteCustomerResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `customerId` | `string` | Template, Required | The ID of the customer to delete. |
| `version` | `?int` | Query, Optional | The current version of the customer profile.<br><br>As a best practice, you should include this parameter to enable [optimistic concurrency](https://developer.squareup.com/docs/working-with-apis/optimistic-concurrency) control.  For more information, see [Delete a customer profile](https://developer.squareup.com/docs/customers-api/use-the-api/keep-records#delete-customer-profile). |

## Requires scope

### oauth2

`CUSTOMERS_WRITE`

## Response Type

**200**: Success

[`DeleteCustomerResponse`](../../doc/models/delete-customer-response.md)

## Example Usage

```php
$customerId = 'customer_id8';

$customersController = $client->getCustomersController();

try {
    $result = $customersController->deleteCustomer($customerId);
    echo 'DeleteCustomerResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Retrieve Customer

Returns details for a single customer.

```php
function retrieveCustomer(string $customerId): RetrieveCustomerResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `customerId` | `string` | Template, Required | The ID of the customer to retrieve. |

## Requires scope

### oauth2

`CUSTOMERS_READ`

## Response Type

**200**: Success

[`RetrieveCustomerResponse`](../../doc/models/retrieve-customer-response.md)

## Example Usage

```php
$customerId = 'customer_id8';

$customersController = $client->getCustomersController();

try {
    $result = $customersController->retrieveCustomer($customerId);
    echo 'RetrieveCustomerResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Update Customer

Updates a customer profile. To change an attribute, specify the new value. To remove an attribute, specify the value as an empty string or empty object.

As a best practice, you should include the `version` field in the request to enable [optimistic concurrency](https://developer.squareup.com/docs/working-with-apis/optimistic-concurrency) control. The value must be set to the current version of the customer profile.

To update a customer profile that was created by merging existing profiles, you must use the ID of the newly created profile.

You cannot use this endpoint to change cards on file. To make changes, use the [Cards API](https://developer.squareup.com/reference/square_2021-08-18/cards-api) or [Gift Cards API](https://developer.squareup.com/reference/square_2021-08-18/gift-cards-api).

```php
function updateCustomer(string $customerId, UpdateCustomerRequest $body): UpdateCustomerResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `customerId` | `string` | Template, Required | The ID of the customer to update. |
| `body` | [`UpdateCustomerRequest`](../../doc/models/update-customer-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`CUSTOMERS_WRITE`

## Response Type

**200**: Success

[`UpdateCustomerResponse`](../../doc/models/update-customer-response.md)

## Example Usage

```php
$customerId = 'customer_id8';

$body = UpdateCustomerRequestBuilder::init()->build();

$customersController = $client->getCustomersController();

try {
    $result = $customersController->updateCustomer(
        $customerId,
        $body
    );
    echo 'UpdateCustomerResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Create Customer Card

Adds a card on file to an existing customer.

As with charges, calls to `CreateCustomerCard` are idempotent. Multiple
calls with the same card nonce return the same card record that was created
with the provided nonce during the _first_ call.

```php
function createCustomerCard(string $customerId, CreateCustomerCardRequest $body): CreateCustomerCardResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `customerId` | `string` | Template, Required | The Square ID of the customer profile the card is linked to. |
| `body` | [`CreateCustomerCardRequest`](../../doc/models/create-customer-card-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`CUSTOMERS_WRITE`

## Response Type

**200**: Success

[`CreateCustomerCardResponse`](../../doc/models/create-customer-card-response.md)

## Example Usage

```php
$customerId = 'customer_id8';

$body = CreateCustomerCardRequestBuilder::init(
    'card_nonce6'
)->build();

$customersController = $client->getCustomersController();

try {
    $result = $customersController->createCustomerCard(
        $customerId,
        $body
    );
    echo 'CreateCustomerCardResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Delete Customer Card

Removes a card on file from a customer.

```php
function deleteCustomerCard(string $customerId, string $cardId): DeleteCustomerCardResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `customerId` | `string` | Template, Required | The ID of the customer that the card on file belongs to. |
| `cardId` | `string` | Template, Required | The ID of the card on file to delete. |

## Requires scope

### oauth2

`CUSTOMERS_WRITE`

## Response Type

**200**: Success

[`DeleteCustomerCardResponse`](../../doc/models/delete-customer-card-response.md)

## Example Usage

```php
$customerId = 'customer_id8';

$cardId = 'card_id4';

$customersController = $client->getCustomersController();

try {
    $result = $customersController->deleteCustomerCard(
        $customerId,
        $cardId
    );
    echo 'DeleteCustomerCardResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Remove Group from Customer

Removes a group membership from a customer.

The customer is identified by the `customer_id` value
and the customer group is identified by the `group_id` value.

```php
function removeGroupFromCustomer(string $customerId, string $groupId): RemoveGroupFromCustomerResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `customerId` | `string` | Template, Required | The ID of the customer to remove from the group. |
| `groupId` | `string` | Template, Required | The ID of the customer group to remove the customer from. |

## Requires scope

### oauth2

`CUSTOMERS_WRITE`

## Response Type

**200**: Success

[`RemoveGroupFromCustomerResponse`](../../doc/models/remove-group-from-customer-response.md)

## Example Usage

```php
$customerId = 'customer_id8';

$groupId = 'group_id0';

$customersController = $client->getCustomersController();

try {
    $result = $customersController->removeGroupFromCustomer(
        $customerId,
        $groupId
    );
    echo 'RemoveGroupFromCustomerResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Add Group to Customer

Adds a group membership to a customer.

The customer is identified by the `customer_id` value
and the customer group is identified by the `group_id` value.

```php
function addGroupToCustomer(string $customerId, string $groupId): AddGroupToCustomerResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `customerId` | `string` | Template, Required | The ID of the customer to add to a group. |
| `groupId` | `string` | Template, Required | The ID of the customer group to add the customer to. |

## Requires scope

### oauth2

`CUSTOMERS_WRITE`

## Response Type

**200**: Success

[`AddGroupToCustomerResponse`](../../doc/models/add-group-to-customer-response.md)

## Example Usage

```php
$customerId = 'customer_id8';

$groupId = 'group_id0';

$customersController = $client->getCustomersController();

try {
    $result = $customersController->addGroupToCustomer(
        $customerId,
        $groupId
    );
    echo 'AddGroupToCustomerResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

