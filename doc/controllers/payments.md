# Payments

```php
$paymentsController = $client->getPaymentsController();
```

## Class Name

`PaymentsController`

## Methods

* [List Payments](../../doc/controllers/payments.md#list-payments)
* [Create Payment](../../doc/controllers/payments.md#create-payment)
* [Cancel Payment by Idempotency Key](../../doc/controllers/payments.md#cancel-payment-by-idempotency-key)
* [Get Payment](../../doc/controllers/payments.md#get-payment)
* [Update Payment](../../doc/controllers/payments.md#update-payment)
* [Cancel Payment](../../doc/controllers/payments.md#cancel-payment)
* [Complete Payment](../../doc/controllers/payments.md#complete-payment)


# List Payments

Retrieves a list of payments taken by the account making the request.

Results are eventually consistent, and new payments or changes to payments might take several
seconds to appear.

The maximum results per page is 100.

```php
function listPayments(
    ?string $beginTime = null,
    ?string $endTime = null,
    ?string $sortOrder = null,
    ?string $cursor = null,
    ?string $locationId = null,
    ?int $total = null,
    ?string $last4 = null,
    ?string $cardBrand = null,
    ?int $limit = null
): ListPaymentsResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `beginTime` | `?string` | Query, Optional | The timestamp for the beginning of the reporting period, in RFC 3339 format.<br>Inclusive. Default: The current time minus one year. |
| `endTime` | `?string` | Query, Optional | The timestamp for the end of the reporting period, in RFC 3339 format.<br><br>Default: The current time. |
| `sortOrder` | `?string` | Query, Optional | The order in which results are listed:<br><br>- `ASC` - Oldest to newest.<br>- `DESC` - Newest to oldest (default). |
| `cursor` | `?string` | Query, Optional | A pagination cursor returned by a previous call to this endpoint.<br>Provide this cursor to retrieve the next set of results for the original query.<br><br>For more information, see [Pagination](https://developer.squareup.com/docs/basics/api101/pagination). |
| `locationId` | `?string` | Query, Optional | Limit results to the location supplied. By default, results are returned<br>for the default (main) location associated with the seller. |
| `total` | `?int` | Query, Optional | The exact amount in the `total_money` for a payment. |
| `last4` | `?string` | Query, Optional | The last four digits of a payment card. |
| `cardBrand` | `?string` | Query, Optional | The brand of the payment card (for example, VISA). |
| `limit` | `?int` | Query, Optional | The maximum number of results to be returned in a single page.<br>It is possible to receive fewer results than the specified limit on a given page.<br><br>The default value of 100 is also the maximum allowed value. If the provided value is<br>greater than 100, it is ignored and the default value is used instead.<br><br>Default: `100` |

## Requires scope

### oauth2

`PAYMENTS_READ`

## Response Type

**200**: Success

[`ListPaymentsResponse`](../../doc/models/list-payments-response.md)

## Example Usage

```php
$paymentsController = $client->getPaymentsController();

try {
    $result = $paymentsController->listPayments();
    echo 'ListPaymentsResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Create Payment

Creates a payment using the provided source. You can use this endpoint
to charge a card (credit/debit card or  
Square gift card) or record a payment that the seller received outside of Square
(cash payment from a buyer or a payment that an external entity
processed on behalf of the seller).

The endpoint creates a
`Payment` object and returns it in the response.

```php
function createPayment(CreatePaymentRequest $body): CreatePaymentResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`CreatePaymentRequest`](../../doc/models/create-payment-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`PAYMENTS_WRITE`

## Response Type

**200**: Success

[`CreatePaymentResponse`](../../doc/models/create-payment-response.md)

## Example Usage

```php
$body = CreatePaymentRequestBuilder::init(
    MoneyBuilder::init()->build(),
    'idempotency_key2',
    'source_id0'
)->build();

$paymentsController = $client->getPaymentsController();

try {
    $result = $paymentsController->createPayment($body);
    echo 'CreatePaymentResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Cancel Payment by Idempotency Key

Cancels (voids) a payment identified by the idempotency key that is specified in the
request.

Use this method when the status of a `CreatePayment` request is unknown (for example, after you send a
`CreatePayment` request, a network error occurs and you do not get a response). In this case, you can
direct Square to cancel the payment using this endpoint. In the request, you provide the same
idempotency key that you provided in your `CreatePayment` request that you want to cancel. After
canceling the payment, you can submit your `CreatePayment` request again.

Note that if no payment with the specified idempotency key is found, no action is taken and the endpoint
returns successfully.

```php
function cancelPaymentByIdempotencyKey(
    CancelPaymentByIdempotencyKeyRequest $body
): CancelPaymentByIdempotencyKeyResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`CancelPaymentByIdempotencyKeyRequest`](../../doc/models/cancel-payment-by-idempotency-key-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`PAYMENTS_WRITE`

## Response Type

**200**: Success

[`CancelPaymentByIdempotencyKeyResponse`](../../doc/models/cancel-payment-by-idempotency-key-response.md)

## Example Usage

```php
$body = CancelPaymentByIdempotencyKeyRequestBuilder::init(
    'idempotency_key2'
)->build();

$paymentsController = $client->getPaymentsController();

try {
    $result = $paymentsController->cancelPaymentByIdempotencyKey($body);
    echo 'CancelPaymentByIdempotencyKeyResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Get Payment

Retrieves details for a specific payment.

```php
function getPayment(string $paymentId): GetPaymentResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `paymentId` | `string` | Template, Required | A unique ID for the desired payment. |

## Requires scope

### oauth2

`PAYMENTS_READ`

## Response Type

**200**: Success

[`GetPaymentResponse`](../../doc/models/get-payment-response.md)

## Example Usage

```php
$paymentId = 'payment_id0';

$paymentsController = $client->getPaymentsController();

try {
    $result = $paymentsController->getPayment($paymentId);
    echo 'GetPaymentResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Update Payment

Updates a payment with the APPROVED status.
You can update the `amount_money` and `tip_money` using this endpoint.

```php
function updatePayment(string $paymentId, UpdatePaymentRequest $body): UpdatePaymentResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `paymentId` | `string` | Template, Required | The ID of the payment to update. |
| `body` | [`UpdatePaymentRequest`](../../doc/models/update-payment-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`PAYMENTS_WRITE`

## Response Type

**200**: Success

[`UpdatePaymentResponse`](../../doc/models/update-payment-response.md)

## Example Usage

```php
$paymentId = 'payment_id0';

$body = UpdatePaymentRequestBuilder::init(
    'idempotency_key2'
)->build();

$paymentsController = $client->getPaymentsController();

try {
    $result = $paymentsController->updatePayment(
        $paymentId,
        $body
    );
    echo 'UpdatePaymentResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Cancel Payment

Cancels (voids) a payment. You can use this endpoint to cancel a payment with
the APPROVED `status`.

```php
function cancelPayment(string $paymentId): CancelPaymentResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `paymentId` | `string` | Template, Required | The ID of the payment to cancel. |

## Requires scope

### oauth2

`PAYMENTS_WRITE`

## Response Type

**200**: Success

[`CancelPaymentResponse`](../../doc/models/cancel-payment-response.md)

## Example Usage

```php
$paymentId = 'payment_id0';

$paymentsController = $client->getPaymentsController();

try {
    $result = $paymentsController->cancelPayment($paymentId);
    echo 'CancelPaymentResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Complete Payment

Completes (captures) a payment.
By default, payments are set to complete immediately after they are created.

You can use this endpoint to complete a payment with the APPROVED `status`.

```php
function completePayment(string $paymentId): CompletePaymentResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `paymentId` | `string` | Template, Required | The unique ID identifying the payment to be completed. |

## Requires scope

### oauth2

`PAYMENTS_WRITE`

## Response Type

**200**: Success

[`CompletePaymentResponse`](../../doc/models/complete-payment-response.md)

## Example Usage

```php
$paymentId = 'payment_id0';

$paymentsController = $client->getPaymentsController();

try {
    $result = $paymentsController->completePayment($paymentId);
    echo 'CompletePaymentResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

