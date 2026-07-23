# Orders

```php
$ordersController = $client->getOrdersController();
```

## Class Name

`OrdersController`

## Methods

* [Create Order](../../doc/controllers/orders.md#create-order)
* [Batch Retrieve Orders](../../doc/controllers/orders.md#batch-retrieve-orders)
* [Calculate Order](../../doc/controllers/orders.md#calculate-order)
* [Search Orders](../../doc/controllers/orders.md#search-orders)
* [Retrieve Order](../../doc/controllers/orders.md#retrieve-order)
* [Update Order](../../doc/controllers/orders.md#update-order)
* [Pay Order](../../doc/controllers/orders.md#pay-order)


# Create Order

Creates a new [order](https://developer.squareup.com/reference/square_2021-08-18/objects/Order) that can include information about products for
purchase and settings to apply to the purchase.

To pay for a created order, see
[Pay for Orders](https://developer.squareup.com/docs/orders-api/pay-for-orders).

You can modify open orders using the [UpdateOrder](https://developer.squareup.com/reference/square_2021-08-18/orders-api/update-order) endpoint.

```php
function createOrder(CreateOrderRequest $body): CreateOrderResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`CreateOrderRequest`](../../doc/models/create-order-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`ORDERS_WRITE`

## Response Type

**200**: Success

[`CreateOrderResponse`](../../doc/models/create-order-response.md)

## Example Usage

```php
$body = CreateOrderRequestBuilder::init()->build();

$ordersController = $client->getOrdersController();

try {
    $result = $ordersController->createOrder($body);
    echo 'CreateOrderResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Batch Retrieve Orders

Retrieves a set of [orders](https://developer.squareup.com/reference/square_2021-08-18/objects/Order) by their IDs.

If a given order ID does not exist, the ID is ignored instead of generating an error.

```php
function batchRetrieveOrders(BatchRetrieveOrdersRequest $body): BatchRetrieveOrdersResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`BatchRetrieveOrdersRequest`](../../doc/models/batch-retrieve-orders-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`ORDERS_READ`

## Response Type

**200**: Success

[`BatchRetrieveOrdersResponse`](../../doc/models/batch-retrieve-orders-response.md)

## Example Usage

```php
$body = BatchRetrieveOrdersRequestBuilder::init(
    [
        'order_ids1'
    ]
)->build();

$ordersController = $client->getOrdersController();

try {
    $result = $ordersController->batchRetrieveOrders($body);
    echo 'BatchRetrieveOrdersResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Calculate Order

Enables applications to preview order pricing without creating an order.

```php
function calculateOrder(CalculateOrderRequest $body): CalculateOrderResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`CalculateOrderRequest`](../../doc/models/calculate-order-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Response Type

**200**: Success

[`CalculateOrderResponse`](../../doc/models/calculate-order-response.md)

## Example Usage

```php
$body = CalculateOrderRequestBuilder::init(
    OrderBuilder::init(
        'location_id0'
    )->build()
)->build();

$ordersController = $client->getOrdersController();

try {
    $result = $ordersController->calculateOrder($body);
    echo 'CalculateOrderResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Search Orders

Search all orders for one or more locations. Orders include all sales,
returns, and exchanges regardless of how or when they entered the Square
ecosystem (such as Point of Sale, Invoices, and Connect APIs).

`SearchOrders` requests need to specify which locations to search and define a
[SearchOrdersQuery](https://developer.squareup.com/reference/square_2021-08-18/objects/SearchOrdersQuery) object that controls
how to sort or filter the results. Your `SearchOrdersQuery` can:

Set filter criteria.
Set the sort order.
Determine whether to return results as complete `Order` objects or as
[OrderEntry](https://developer.squareup.com/reference/square_2021-08-18/objects/OrderEntry) objects.

Note that details for orders processed with Square Point of Sale while in
offline mode might not be transmitted to Square for up to 72 hours. Offline
orders have a `created_at` value that reflects the time the order was created,
not the time it was subsequently transmitted to Square.

```php
function searchOrders(SearchOrdersRequest $body): SearchOrdersResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`SearchOrdersRequest`](../../doc/models/search-orders-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`ORDERS_READ`

## Response Type

**200**: Success

[`SearchOrdersResponse`](../../doc/models/search-orders-response.md)

## Example Usage

```php
$body = SearchOrdersRequestBuilder::init()->build();

$ordersController = $client->getOrdersController();

try {
    $result = $ordersController->searchOrders($body);
    echo 'SearchOrdersResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Retrieve Order

Retrieves an [Order](https://developer.squareup.com/reference/square_2021-08-18/objects/Order) by ID.

```php
function retrieveOrder(string $orderId): RetrieveOrderResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `orderId` | `string` | Template, Required | The ID of the order to retrieve. |

## Requires scope

### oauth2

`ORDERS_READ`

## Response Type

**200**: Success

[`RetrieveOrderResponse`](../../doc/models/retrieve-order-response.md)

## Example Usage

```php
$orderId = 'order_id6';

$ordersController = $client->getOrdersController();

try {
    $result = $ordersController->retrieveOrder($orderId);
    echo 'RetrieveOrderResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Update Order

Updates an open [order](https://developer.squareup.com/reference/square_2021-08-18/objects/Order) by adding, replacing, or deleting
fields. Orders with a `COMPLETED` or `CANCELED` state cannot be updated.

An `UpdateOrder` request requires the following:

- The `order_id` in the endpoint path, identifying the order to update.
- The latest `version` of the order to update.
- The [sparse order](https://developer.squareup.com/docs/orders-api/manage-orders#sparse-order-objects)
  containing only the fields to update and the version to which the update is
  being applied.
- If deleting fields, the [dot notation paths](https://developer.squareup.com/docs/orders-api/manage-orders#on-dot-notation)
  identifying the fields to clear.

To pay for an order, see
[Pay for Orders](https://developer.squareup.com/docs/orders-api/pay-for-orders).

```php
function updateOrder(string $orderId, UpdateOrderRequest $body): UpdateOrderResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `orderId` | `string` | Template, Required | The ID of the order to update. |
| `body` | [`UpdateOrderRequest`](../../doc/models/update-order-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`ORDERS_WRITE`

## Response Type

**200**: Success

[`UpdateOrderResponse`](../../doc/models/update-order-response.md)

## Example Usage

```php
$orderId = 'order_id6';

$body = UpdateOrderRequestBuilder::init()->build();

$ordersController = $client->getOrdersController();

try {
    $result = $ordersController->updateOrder(
        $orderId,
        $body
    );
    echo 'UpdateOrderResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Pay Order

Pay for an [order](https://developer.squareup.com/reference/square_2021-08-18/objects/Order) using one or more approved [payments](https://developer.squareup.com/reference/square_2021-08-18/objects/Payment)
or settle an order with a total of `0`.

The total of the `payment_ids` listed in the request must be equal to the order
total. Orders with a total amount of `0` can be marked as paid by specifying an empty
array of `payment_ids` in the request.

To be used with `PayOrder`, a payment must:

- Reference the order by specifying the `order_id` when [creating the payment](https://developer.squareup.com/reference/square_2021-08-18/payments-api/create-payment).
  Any approved payments that reference the same `order_id` not specified in the
  `payment_ids` is canceled.
- Be approved with [delayed capture](https://developer.squareup.com/docs/payments-api/take-payments#delayed-capture).
  Using a delayed capture payment with `PayOrder` completes the approved payment.

```php
function payOrder(string $orderId, PayOrderRequest $body): PayOrderResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `orderId` | `string` | Template, Required | The ID of the order being paid. |
| `body` | [`PayOrderRequest`](../../doc/models/pay-order-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`ORDERS_WRITE`, `PAYMENTS_WRITE`

## Response Type

**200**: Success

[`PayOrderResponse`](../../doc/models/pay-order-response.md)

## Example Usage

```php
$orderId = 'order_id6';

$body = PayOrderRequestBuilder::init(
    'idempotency_key2'
)->build();

$ordersController = $client->getOrdersController();

try {
    $result = $ordersController->payOrder(
        $orderId,
        $body
    );
    echo 'PayOrderResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

