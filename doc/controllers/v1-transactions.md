# V1 Transactions

```php
$v1TransactionsController = $client->getV1TransactionsController();
```

## Class Name

`V1TransactionsController`

## Methods

* [List Orders](../../doc/controllers/v1-transactions.md#list-orders)
* [Retrieve Order](../../doc/controllers/v1-transactions.md#retrieve-order)
* [Update Order](../../doc/controllers/v1-transactions.md#update-order)
* [List Payments](../../doc/controllers/v1-transactions.md#list-payments)
* [Retrieve Payment](../../doc/controllers/v1-transactions.md#retrieve-payment)
* [List Refunds](../../doc/controllers/v1-transactions.md#list-refunds)
* [Create Refund](../../doc/controllers/v1-transactions.md#create-refund)
* [List Settlements](../../doc/controllers/v1-transactions.md#list-settlements)
* [Retrieve Settlement](../../doc/controllers/v1-transactions.md#retrieve-settlement)


# List Orders

Provides summary information for a merchant's online store orders.

```php
function listOrders(
    string $locationId,
    ?string $order = null,
    ?int $limit = null,
    ?string $batchToken = null
): array
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `locationId` | `string` | Template, Required | The ID of the location to list online store orders for. |
| `order` | `?string` | Query, Optional | The order in which payments are listed in the response. |
| `limit` | `?int` | Query, Optional | The maximum number of payments to return in a single response. This value cannot exceed 200. |
| `batchToken` | `?string` | Query, Optional | A pagination cursor to retrieve the next set of results for your<br>original query to the endpoint. |

## Requires scope

### oauth2

`ORDERS_READ`

## Response Type

**200**: Success

[`V1Order[]`](../../doc/models/v1-order.md)

## Example Usage

```php
$locationId = 'location_id4';

$v1TransactionsController = $client->getV1TransactionsController();

try {
    $result = $v1TransactionsController->listOrders($locationId);
    echo 'V1Order[]:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Retrieve Order

Provides comprehensive information for a single online store order, including the order's history.

```php
function retrieveOrder(string $locationId, string $orderId): V1Order
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `locationId` | `string` | Template, Required | The ID of the order's associated location. |
| `orderId` | `string` | Template, Required | The order's Square-issued ID. You obtain this value from Order objects returned by the List Orders endpoint |

## Requires scope

### oauth2

`ORDERS_READ`

## Response Type

**200**: Success

[`V1Order`](../../doc/models/v1-order.md)

## Example Usage

```php
$locationId = 'location_id4';

$orderId = 'order_id6';

$v1TransactionsController = $client->getV1TransactionsController();

try {
    $result = $v1TransactionsController->retrieveOrder(
        $locationId,
        $orderId
    );
    echo 'V1Order:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Update Order

Updates the details of an online store order. Every update you perform on an order corresponds to one of three actions:

```php
function updateOrder(string $locationId, string $orderId, V1UpdateOrderRequest $body): V1Order
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `locationId` | `string` | Template, Required | The ID of the order's associated location. |
| `orderId` | `string` | Template, Required | The order's Square-issued ID. You obtain this value from Order objects returned by the List Orders endpoint |
| `body` | [`V1UpdateOrderRequest`](../../doc/models/v1-update-order-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`ORDERS_WRITE`

## Response Type

**200**: Success

[`V1Order`](../../doc/models/v1-order.md)

## Example Usage

```php
$locationId = 'location_id4';

$orderId = 'order_id6';

$body = V1UpdateOrderRequestBuilder::init(
    'action6'
)->build();

$v1TransactionsController = $client->getV1TransactionsController();

try {
    $result = $v1TransactionsController->updateOrder(
        $locationId,
        $orderId,
        $body
    );
    echo 'V1Order:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# List Payments

Provides summary information for all payments taken for a given
Square account during a date range. Date ranges cannot exceed 1 year in
length. See Date ranges for details of inclusive and exclusive dates.

*Note**: Details for payments processed with Square Point of Sale while
in offline mode may not be transmitted to Square for up to 72 hours.
Offline payments have a `created_at` value that reflects the time the
payment was originally processed, not the time it was subsequently
transmitted to Square. Consequently, the ListPayments endpoint might
list an offline payment chronologically between online payments that
were seen in a previous request.

```php
function listPayments(
    string $locationId,
    ?string $order = null,
    ?string $beginTime = null,
    ?string $endTime = null,
    ?int $limit = null,
    ?string $batchToken = null,
    ?bool $includePartial = null
): array
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `locationId` | `string` | Template, Required | The ID of the location to list payments for. If you specify me, this endpoint returns payments aggregated from all of the business's locations. |
| `order` | `?string` | Query, Optional | The order in which payments are listed in the response. |
| `beginTime` | `?string` | Query, Optional | The beginning of the requested reporting period, in ISO 8601 format. If this value is before January 1, 2013 (2013-01-01T00:00:00Z), this endpoint returns an error. Default value: The current time minus one year. |
| `endTime` | `?string` | Query, Optional | The end of the requested reporting period, in ISO 8601 format. If this value is more than one year greater than begin_time, this endpoint returns an error. Default value: The current time. |
| `limit` | `?int` | Query, Optional | The maximum number of payments to return in a single response. This value cannot exceed 200. |
| `batchToken` | `?string` | Query, Optional | A pagination cursor to retrieve the next set of results for your<br>original query to the endpoint. |
| `includePartial` | `?bool` | Query, Optional | Indicates whether or not to include partial payments in the response. Partial payments will have the tenders collected so far, but the itemizations will be empty until the payment is completed. |

## Requires scope

### oauth2

`PAYMENTS_READ`

## Response Type

**200**: Success

[`V1Payment[]`](../../doc/models/v1-payment.md)

## Example Usage

```php
$locationId = 'location_id4';

$v1TransactionsController = $client->getV1TransactionsController();

try {
    $result = $v1TransactionsController->listPayments($locationId);
    echo 'V1Payment[]:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Retrieve Payment

Provides comprehensive information for a single payment.

```php
function retrievePayment(string $locationId, string $paymentId): V1Payment
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `locationId` | `string` | Template, Required | The ID of the payment's associated location. |
| `paymentId` | `string` | Template, Required | The Square-issued payment ID. payment_id comes from Payment objects returned by the List Payments endpoint, Settlement objects returned by the List Settlements endpoint, or Refund objects returned by the List Refunds endpoint. |

## Requires scope

### oauth2

`PAYMENTS_READ`

## Response Type

**200**: Success

[`V1Payment`](../../doc/models/v1-payment.md)

## Example Usage

```php
$locationId = 'location_id4';

$paymentId = 'payment_id0';

$v1TransactionsController = $client->getV1TransactionsController();

try {
    $result = $v1TransactionsController->retrievePayment(
        $locationId,
        $paymentId
    );
    echo 'V1Payment:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# List Refunds

Provides the details for all refunds initiated by a merchant or any of the merchant's mobile staff during a date range. Date ranges cannot exceed one year in length.

```php
function listRefunds(
    string $locationId,
    ?string $order = null,
    ?string $beginTime = null,
    ?string $endTime = null,
    ?int $limit = null,
    ?string $batchToken = null
): array
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `locationId` | `string` | Template, Required | The ID of the location to list refunds for. |
| `order` | `?string` | Query, Optional | The order in which payments are listed in the response. |
| `beginTime` | `?string` | Query, Optional | The beginning of the requested reporting period, in ISO 8601 format. If this value is before January 1, 2013 (2013-01-01T00:00:00Z), this endpoint returns an error. Default value: The current time minus one year. |
| `endTime` | `?string` | Query, Optional | The end of the requested reporting period, in ISO 8601 format. If this value is more than one year greater than begin_time, this endpoint returns an error. Default value: The current time. |
| `limit` | `?int` | Query, Optional | The approximate number of refunds to return in a single response. Default: 100. Max: 200. Response may contain more results than the prescribed limit when refunds are made simultaneously to multiple tenders in a payment or when refunds are generated in an exchange to account for the value of returned goods. |
| `batchToken` | `?string` | Query, Optional | A pagination cursor to retrieve the next set of results for your<br>original query to the endpoint. |

## Requires scope

### oauth2

`PAYMENTS_READ`

## Response Type

**200**: Success

[`V1Refund[]`](../../doc/models/v1-refund.md)

## Example Usage

```php
$locationId = 'location_id4';

$v1TransactionsController = $client->getV1TransactionsController();

try {
    $result = $v1TransactionsController->listRefunds($locationId);
    echo 'V1Refund[]:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Create Refund

Issues a refund for a previously processed payment. You must issue
a refund within 60 days of the associated payment.

You cannot issue a partial refund for a split tender payment. You must
instead issue a full or partial refund for a particular tender, by
providing the applicable tender id to the V1CreateRefund endpoint.
Issuing a full refund for a split tender payment refunds all tenders
associated with the payment.

Issuing a refund for a card payment is not reversible. For development
purposes, you can create fake cash payments in Square Point of Sale and
refund them.

```php
function createRefund(string $locationId, V1CreateRefundRequest $body): V1Refund
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `locationId` | `string` | Template, Required | The ID of the original payment's associated location. |
| `body` | [`V1CreateRefundRequest`](../../doc/models/v1-create-refund-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`PAYMENTS_WRITE`

## Response Type

**200**: Success

[`V1Refund`](../../doc/models/v1-refund.md)

## Example Usage

```php
$locationId = 'location_id4';

$body = V1CreateRefundRequestBuilder::init(
    'payment_id6',
    'reason8',
    'type4'
)->build();

$v1TransactionsController = $client->getV1TransactionsController();

try {
    $result = $v1TransactionsController->createRefund(
        $locationId,
        $body
    );
    echo 'V1Refund:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# List Settlements

Provides summary information for all deposits and withdrawals
initiated by Square to a linked bank account during a date range. Date
ranges cannot exceed one year in length.

*Note**: the ListSettlements endpoint does not provide entry
information.

```php
function listSettlements(
    string $locationId,
    ?string $order = null,
    ?string $beginTime = null,
    ?string $endTime = null,
    ?int $limit = null,
    ?string $status = null,
    ?string $batchToken = null
): array
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `locationId` | `string` | Template, Required | The ID of the location to list settlements for. If you specify me, this endpoint returns settlements aggregated from all of the business's locations. |
| `order` | `?string` | Query, Optional | The order in which settlements are listed in the response. |
| `beginTime` | `?string` | Query, Optional | The beginning of the requested reporting period, in ISO 8601 format. If this value is before January 1, 2013 (2013-01-01T00:00:00Z), this endpoint returns an error. Default value: The current time minus one year. |
| `endTime` | `?string` | Query, Optional | The end of the requested reporting period, in ISO 8601 format. If this value is more than one year greater than begin_time, this endpoint returns an error. Default value: The current time. |
| `limit` | `?int` | Query, Optional | The maximum number of settlements to return in a single response. This value cannot exceed 200. |
| `status` | `?string` | Query, Optional | Provide this parameter to retrieve only settlements with a particular status (SENT or FAILED). |
| `batchToken` | `?string` | Query, Optional | A pagination cursor to retrieve the next set of results for your<br>original query to the endpoint. |

## Requires scope

### oauth2

`SETTLEMENTS_READ`

## Response Type

**200**: Success

[`V1Settlement[]`](../../doc/models/v1-settlement.md)

## Example Usage

```php
$locationId = 'location_id4';

$v1TransactionsController = $client->getV1TransactionsController();

try {
    $result = $v1TransactionsController->listSettlements($locationId);
    echo 'V1Settlement[]:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Retrieve Settlement

Provides comprehensive information for a single settlement.

The returned `Settlement` objects include an `entries` field that lists
the transactions that contribute to the settlement total. Most
settlement entries correspond to a payment payout, but settlement
entries are also generated for less common events, like refunds, manual
adjustments, or chargeback holds.

Square initiates its regular deposits as indicated in the
[Deposit Options with Square](https://squareup.com/help/us/en/article/3807)
help article. Details for a regular deposit are usually not available
from Connect API endpoints before 10 p.m. PST the same day.

Square does not know when an initiated settlement **completes**, only
whether it has failed. A completed settlement is typically reflected in
a bank account within 3 business days, but in exceptional cases it may
take longer.

```php
function retrieveSettlement(string $locationId, string $settlementId): V1Settlement
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `locationId` | `string` | Template, Required | The ID of the settlements's associated location. |
| `settlementId` | `string` | Template, Required | The settlement's Square-issued ID. You obtain this value from Settlement objects returned by the List Settlements endpoint. |

## Requires scope

### oauth2

`SETTLEMENTS_READ`

## Response Type

**200**: Success

[`V1Settlement`](../../doc/models/v1-settlement.md)

## Example Usage

```php
$locationId = 'location_id4';

$settlementId = 'settlement_id0';

$v1TransactionsController = $client->getV1TransactionsController();

try {
    $result = $v1TransactionsController->retrieveSettlement(
        $locationId,
        $settlementId
    );
    echo 'V1Settlement:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

