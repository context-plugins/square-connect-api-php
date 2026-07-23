# Transactions

```php
$transactionsController = $client->getTransactionsController();
```

## Class Name

`TransactionsController`

## Methods

* [List Refunds](../../doc/controllers/transactions.md#list-refunds)
* [List Transactions](../../doc/controllers/transactions.md#list-transactions)
* [Charge](../../doc/controllers/transactions.md#charge)
* [Retrieve Transaction](../../doc/controllers/transactions.md#retrieve-transaction)
* [Capture Transaction](../../doc/controllers/transactions.md#capture-transaction)
* [Create Refund](../../doc/controllers/transactions.md#create-refund)
* [Void Transaction](../../doc/controllers/transactions.md#void-transaction)


# List Refunds

Lists refunds for one of a business's locations.

In addition to full or partial tender refunds processed through Square APIs,
refunds may result from itemized returns or exchanges through Square's
Point of Sale applications.

Refunds with a `status` of `PENDING` are not currently included in this
endpoint's response.

Max results per [page](https://developer.squareup.com/docs/working-with-apis/pagination): 50

```php
function listRefunds(
    string $locationId,
    ?string $beginTime = null,
    ?string $endTime = null,
    ?string $sortOrder = null,
    ?string $cursor = null
): ListRefundsResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `locationId` | `string` | Template, Required | The ID of the location to list refunds for. |
| `beginTime` | `?string` | Query, Optional | The beginning of the requested reporting period, in RFC 3339 format.<br><br>See [Date ranges](https://developer.squareup.com/docs/build-basics/working-with-dates) for details on date inclusivity/exclusivity.<br><br>Default value: The current time minus one year. |
| `endTime` | `?string` | Query, Optional | The end of the requested reporting period, in RFC 3339 format.<br><br>See [Date ranges](https://developer.squareup.com/docs/build-basics/working-with-dates) for details on date inclusivity/exclusivity.<br><br>Default value: The current time. |
| `sortOrder` | `?string` | Query, Optional | The order in which results are listed in the response (`ASC` for<br>oldest first, `DESC` for newest first).<br><br>Default value: `DESC` |
| `cursor` | `?string` | Query, Optional | A pagination cursor returned by a previous call to this endpoint.<br>Provide this to retrieve the next set of results for your original query.<br><br>See [Paginating results](https://developer.squareup.com/docs/working-with-apis/pagination) for more information. |

## Requires scope

### oauth2

`PAYMENTS_READ`

## Response Type

**200**: Success

[`ListRefundsResponse`](../../doc/models/list-refunds-response.md)

## Example Usage

```php
$locationId = 'location_id4';

$transactionsController = $client->getTransactionsController();

try {
    $result = $transactionsController->listRefunds($locationId);
    echo 'ListRefundsResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# List Transactions

Lists transactions for a particular location.

Transactions include payment information from sales and exchanges and refund
information from returns and exchanges.

Max results per [page](https://developer.squareup.com/docs/working-with-apis/pagination): 50

```php
function listTransactions(
    string $locationId,
    ?string $beginTime = null,
    ?string $endTime = null,
    ?string $sortOrder = null,
    ?string $cursor = null
): ListTransactionsResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `locationId` | `string` | Template, Required | The ID of the location to list transactions for. |
| `beginTime` | `?string` | Query, Optional | The beginning of the requested reporting period, in RFC 3339 format.<br><br>See [Date ranges](https://developer.squareup.com/docs/build-basics/working-with-dates) for details on date inclusivity/exclusivity.<br><br>Default value: The current time minus one year. |
| `endTime` | `?string` | Query, Optional | The end of the requested reporting period, in RFC 3339 format.<br><br>See [Date ranges](https://developer.squareup.com/docs/build-basics/working-with-dates) for details on date inclusivity/exclusivity.<br><br>Default value: The current time. |
| `sortOrder` | `?string` | Query, Optional | The order in which results are listed in the response (`ASC` for<br>oldest first, `DESC` for newest first).<br><br>Default value: `DESC` |
| `cursor` | `?string` | Query, Optional | A pagination cursor returned by a previous call to this endpoint.<br>Provide this to retrieve the next set of results for your original query.<br><br>See [Paginating results](https://developer.squareup.com/docs/working-with-apis/pagination) for more information. |

## Requires scope

### oauth2

`PAYMENTS_READ`

## Response Type

**200**: Success

[`ListTransactionsResponse`](../../doc/models/list-transactions-response.md)

## Example Usage

```php
$locationId = 'location_id4';

$transactionsController = $client->getTransactionsController();

try {
    $result = $transactionsController->listTransactions($locationId);
    echo 'ListTransactionsResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Charge

Charges a card represented by a card nonce or a customer's card on file.

Your request to this endpoint must include _either_:

- A value for the `card_nonce` parameter (to charge a card payment token generated
  with the Web Payments SDK)
- Values for the `customer_card_id` and `customer_id` parameters (to charge
  a customer's card on file)

In order for an eCommerce payment to potentially qualify for
[Square chargeback protection](https://squareup.com/help/article/5394), you
_must_ provide values for the following parameters in your request:

- `buyer_email_address`
- At least one of `billing_address` or `shipping_address`

When this response is returned, the amount of Square's processing fee might not yet be
calculated. To obtain the processing fee, wait about ten seconds and call
[RetrieveTransaction](https://developer.squareup.com/reference/square_2021-08-18/transactions-api/retrieve-transaction). See the `processing_fee_money`
field of each [Tender included](https://developer.squareup.com/reference/square_2021-08-18/objects/Tender) in the transaction.

```php
function charge(string $locationId, ChargeRequest $body): ChargeResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `locationId` | `string` | Template, Required | The ID of the location to associate the created transaction with. |
| `body` | [`ChargeRequest`](../../doc/models/charge-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`PAYMENTS_WRITE`

## Response Type

**200**: Success

[`ChargeResponse`](../../doc/models/charge-response.md)

## Example Usage

```php
$locationId = 'location_id4';

$body = ChargeRequestBuilder::init(
    MoneyBuilder::init()->build(),
    'idempotency_key2'
)->build();

$transactionsController = $client->getTransactionsController();

try {
    $result = $transactionsController->charge(
        $locationId,
        $body
    );
    echo 'ChargeResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Retrieve Transaction

Retrieves details for a single transaction.

```php
function retrieveTransaction(string $locationId, string $transactionId): RetrieveTransactionResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `locationId` | `string` | Template, Required | The ID of the transaction's associated location. |
| `transactionId` | `string` | Template, Required | The ID of the transaction to retrieve. |

## Requires scope

### oauth2

`PAYMENTS_READ`

## Response Type

**200**: Success

[`RetrieveTransactionResponse`](../../doc/models/retrieve-transaction-response.md)

## Example Usage

```php
$locationId = 'location_id4';

$transactionId = 'transaction_id8';

$transactionsController = $client->getTransactionsController();

try {
    $result = $transactionsController->retrieveTransaction(
        $locationId,
        $transactionId
    );
    echo 'RetrieveTransactionResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Capture Transaction

Captures a transaction that was created with the [Charge](https://developer.squareup.com/reference/square_2021-08-18/transactions-api/charge)
endpoint with a `delay_capture` value of `true`.

See [Delayed capture transactions](https://developer.squareup.com/docs/payments/transactions/overview#delayed-capture)
for more information.

```php
function captureTransaction(string $locationId, string $transactionId): CaptureTransactionResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `locationId` | `string` | Template, Required | - |
| `transactionId` | `string` | Template, Required | - |

## Requires scope

### oauth2

`PAYMENTS_WRITE`

## Response Type

**200**: Success

[`CaptureTransactionResponse`](../../doc/models/capture-transaction-response.md)

## Example Usage

```php
$locationId = 'location_id4';

$transactionId = 'transaction_id8';

$transactionsController = $client->getTransactionsController();

try {
    $result = $transactionsController->captureTransaction(
        $locationId,
        $transactionId
    );
    echo 'CaptureTransactionResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Create Refund

Initiates a refund for a previously charged tender.

You must issue a refund within 120 days of the associated payment. See
[this article](https://squareup.com/help/us/en/article/5060) for more information
on refund behavior.

NOTE: Card-present transactions with Interac credit cards **cannot be
refunded using the Connect API**. Interac transactions must refunded
in-person (e.g., dipping the card using POS app).

```php
function createRefund(
    string $locationId,
    string $transactionId,
    CreateRefundRequest $body
): CreateRefundResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `locationId` | `string` | Template, Required | The ID of the original transaction's associated location. |
| `transactionId` | `string` | Template, Required | The ID of the original transaction that includes the tender to refund. |
| `body` | [`CreateRefundRequest`](../../doc/models/create-refund-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`PAYMENTS_WRITE`

## Response Type

**200**: Success

[`CreateRefundResponse`](../../doc/models/create-refund-response.md)

## Example Usage

```php
$locationId = 'location_id4';

$transactionId = 'transaction_id8';

$body = CreateRefundRequestBuilder::init(
    MoneyBuilder::init()->build(),
    'idempotency_key2',
    'tender_id4'
)->build();

$transactionsController = $client->getTransactionsController();

try {
    $result = $transactionsController->createRefund(
        $locationId,
        $transactionId,
        $body
    );
    echo 'CreateRefundResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Void Transaction

Cancels a transaction that was created with the [Charge](https://developer.squareup.com/reference/square_2021-08-18/transactions-api/charge)
endpoint with a `delay_capture` value of `true`.

See [Delayed capture transactions](https://developer.squareup.com/docs/payments/transactions/overview#delayed-capture)
for more information.

```php
function voidTransaction(string $locationId, string $transactionId): VoidTransactionResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `locationId` | `string` | Template, Required | - |
| `transactionId` | `string` | Template, Required | - |

## Requires scope

### oauth2

`PAYMENTS_WRITE`

## Response Type

**200**: Success

[`VoidTransactionResponse`](../../doc/models/void-transaction-response.md)

## Example Usage

```php
$locationId = 'location_id4';

$transactionId = 'transaction_id8';

$transactionsController = $client->getTransactionsController();

try {
    $result = $transactionsController->voidTransaction(
        $locationId,
        $transactionId
    );
    echo 'VoidTransactionResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

