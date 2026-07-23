# Terminal

```php
$terminalController = $client->getTerminalController();
```

## Class Name

`TerminalController`

## Methods

* [Create Terminal Checkout](../../doc/controllers/terminal.md#create-terminal-checkout)
* [Search Terminal Checkouts](../../doc/controllers/terminal.md#search-terminal-checkouts)
* [Get Terminal Checkout](../../doc/controllers/terminal.md#get-terminal-checkout)
* [Cancel Terminal Checkout](../../doc/controllers/terminal.md#cancel-terminal-checkout)
* [Create Terminal Refund](../../doc/controllers/terminal.md#create-terminal-refund)
* [Search Terminal Refunds](../../doc/controllers/terminal.md#search-terminal-refunds)
* [Get Terminal Refund](../../doc/controllers/terminal.md#get-terminal-refund)
* [Cancel Terminal Refund](../../doc/controllers/terminal.md#cancel-terminal-refund)


# Create Terminal Checkout

Creates a Terminal checkout request and sends it to the specified device to take a payment
for the requested amount.

```php
function createTerminalCheckout(CreateTerminalCheckoutRequest $body): CreateTerminalCheckoutResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`CreateTerminalCheckoutRequest`](../../doc/models/create-terminal-checkout-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`PAYMENTS_WRITE`

## Response Type

**200**: Success

[`CreateTerminalCheckoutResponse`](../../doc/models/create-terminal-checkout-response.md)

## Example Usage

```php
$body = CreateTerminalCheckoutRequestBuilder::init(
    TerminalCheckoutBuilder::init(
        MoneyBuilder::init()->build(),
        DeviceCheckoutOptionsBuilder::init(
            'device_id6'
        )->build()
    )->build(),
    'idempotency_key2'
)->build();

$terminalController = $client->getTerminalController();

try {
    $result = $terminalController->createTerminalCheckout($body);
    echo 'CreateTerminalCheckoutResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Search Terminal Checkouts

Retrieves a filtered list of Terminal checkout requests created by the account making the request.

```php
function searchTerminalCheckouts(SearchTerminalCheckoutsRequest $body): SearchTerminalCheckoutsResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`SearchTerminalCheckoutsRequest`](../../doc/models/search-terminal-checkouts-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`PAYMENTS_READ`

## Response Type

**200**: Success

[`SearchTerminalCheckoutsResponse`](../../doc/models/search-terminal-checkouts-response.md)

## Example Usage

```php
$body = SearchTerminalCheckoutsRequestBuilder::init()->build();

$terminalController = $client->getTerminalController();

try {
    $result = $terminalController->searchTerminalCheckouts($body);
    echo 'SearchTerminalCheckoutsResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Get Terminal Checkout

Retrieves a Terminal checkout request by `checkout_id`.

```php
function getTerminalCheckout(string $checkoutId): GetTerminalCheckoutResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `checkoutId` | `string` | Template, Required | The unique ID for the desired `TerminalCheckout`. |

## Requires scope

### oauth2

`PAYMENTS_READ`

## Response Type

**200**: Success

[`GetTerminalCheckoutResponse`](../../doc/models/get-terminal-checkout-response.md)

## Example Usage

```php
$checkoutId = 'checkout_id8';

$terminalController = $client->getTerminalController();

try {
    $result = $terminalController->getTerminalCheckout($checkoutId);
    echo 'GetTerminalCheckoutResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Cancel Terminal Checkout

Cancels a Terminal checkout request if the status of the request permits it.

```php
function cancelTerminalCheckout(string $checkoutId): CancelTerminalCheckoutResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `checkoutId` | `string` | Template, Required | The unique ID for the desired `TerminalCheckout`. |

## Requires scope

### oauth2

`PAYMENTS_WRITE`

## Response Type

**200**: Success

[`CancelTerminalCheckoutResponse`](../../doc/models/cancel-terminal-checkout-response.md)

## Example Usage

```php
$checkoutId = 'checkout_id8';

$terminalController = $client->getTerminalController();

try {
    $result = $terminalController->cancelTerminalCheckout($checkoutId);
    echo 'CancelTerminalCheckoutResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Create Terminal Refund

Creates a request to refund an Interac payment completed on a Square Terminal.

```php
function createTerminalRefund(CreateTerminalRefundRequest $body): CreateTerminalRefundResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`CreateTerminalRefundRequest`](../../doc/models/create-terminal-refund-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`PAYMENTS_WRITE`

## Response Type

**200**: Success

[`CreateTerminalRefundResponse`](../../doc/models/create-terminal-refund-response.md)

## Example Usage

```php
$body = CreateTerminalRefundRequestBuilder::init(
    'idempotency_key2'
)->build();

$terminalController = $client->getTerminalController();

try {
    $result = $terminalController->createTerminalRefund($body);
    echo 'CreateTerminalRefundResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Search Terminal Refunds

Retrieves a filtered list of Interac Terminal refund requests created by the seller making the request.

```php
function searchTerminalRefunds(SearchTerminalRefundsRequest $body): SearchTerminalRefundsResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`SearchTerminalRefundsRequest`](../../doc/models/search-terminal-refunds-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`PAYMENTS_READ`

## Response Type

**200**: Success

[`SearchTerminalRefundsResponse`](../../doc/models/search-terminal-refunds-response.md)

## Example Usage

```php
$body = SearchTerminalRefundsRequestBuilder::init()->build();

$terminalController = $client->getTerminalController();

try {
    $result = $terminalController->searchTerminalRefunds($body);
    echo 'SearchTerminalRefundsResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Get Terminal Refund

Retrieves an Interac Terminal refund object by ID.

```php
function getTerminalRefund(string $terminalRefundId): GetTerminalRefundResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `terminalRefundId` | `string` | Template, Required | The unique ID for the desired `TerminalRefund`. |

## Requires scope

### oauth2

`PAYMENTS_READ`

## Response Type

**200**: Success

[`GetTerminalRefundResponse`](../../doc/models/get-terminal-refund-response.md)

## Example Usage

```php
$terminalRefundId = 'terminal_refund_id0';

$terminalController = $client->getTerminalController();

try {
    $result = $terminalController->getTerminalRefund($terminalRefundId);
    echo 'GetTerminalRefundResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Cancel Terminal Refund

Cancels an Interac Terminal refund request by refund request ID if the status of the request permits it.

```php
function cancelTerminalRefund(string $terminalRefundId): CancelTerminalRefundResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `terminalRefundId` | `string` | Template, Required | The unique ID for the desired `TerminalRefund`. |

## Requires scope

### oauth2

`PAYMENTS_WRITE`

## Response Type

**200**: Success

[`CancelTerminalRefundResponse`](../../doc/models/cancel-terminal-refund-response.md)

## Example Usage

```php
$terminalRefundId = 'terminal_refund_id0';

$terminalController = $client->getTerminalController();

try {
    $result = $terminalController->cancelTerminalRefund($terminalRefundId);
    echo 'CancelTerminalRefundResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

