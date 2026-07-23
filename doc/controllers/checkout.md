# Checkout

```php
$checkoutController = $client->getCheckoutController();
```

## Class Name

`CheckoutController`


# Create Checkout

Links a `checkoutId` to a `checkout_page_url` that customers are
directed to in order to provide their payment information using a
payment processing workflow hosted on connect.squareup.com.

```php
function createCheckout(string $locationId, CreateCheckoutRequest $body): CreateCheckoutResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `locationId` | `string` | Template, Required | The ID of the business location to associate the checkout with. |
| `body` | [`CreateCheckoutRequest`](../../doc/models/create-checkout-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`ORDERS_WRITE`, `PAYMENTS_WRITE`

## Response Type

**200**: Success

[`CreateCheckoutResponse`](../../doc/models/create-checkout-response.md)

## Example Usage

```php
$locationId = 'location_id4';

$body = CreateCheckoutRequestBuilder::init(
    'idempotency_key2',
    CreateOrderRequestBuilder::init()->build()
)->build();

$checkoutController = $client->getCheckoutController();

try {
    $result = $checkoutController->createCheckout(
        $locationId,
        $body
    );
    echo 'CreateCheckoutResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

