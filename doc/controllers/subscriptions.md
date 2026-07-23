# Subscriptions

```php
$subscriptionsController = $client->getSubscriptionsController();
```

## Class Name

`SubscriptionsController`

## Methods

* [Create Subscription](../../doc/controllers/subscriptions.md#create-subscription)
* [Search Subscriptions](../../doc/controllers/subscriptions.md#search-subscriptions)
* [Retrieve Subscription](../../doc/controllers/subscriptions.md#retrieve-subscription)
* [Update Subscription](../../doc/controllers/subscriptions.md#update-subscription)
* [Cancel Subscription](../../doc/controllers/subscriptions.md#cancel-subscription)
* [List Subscription Events](../../doc/controllers/subscriptions.md#list-subscription-events)
* [Resume Subscription](../../doc/controllers/subscriptions.md#resume-subscription)


# Create Subscription

Creates a subscription for a customer to a subscription plan.

If you provide a card on file in the request, Square charges the card for
the subscription. Otherwise, Square bills an invoice to the customer's email
address. The subscription starts immediately, unless the request includes
the optional `start_date`. Each individual subscription is associated with a particular location.

```php
function createSubscription(CreateSubscriptionRequest $body): CreateSubscriptionResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`CreateSubscriptionRequest`](../../doc/models/create-subscription-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`CUSTOMERS_READ`, `INVOICES_WRITE`, `ITEMS_READ`, `ORDERS_WRITE`, `PAYMENTS_WRITE`, `SUBSCRIPTIONS_WRITE`

## Response Type

**200**: Success

[`CreateSubscriptionResponse`](../../doc/models/create-subscription-response.md)

## Example Usage

```php
$body = CreateSubscriptionRequestBuilder::init(
    'customer_id4',
    'location_id0',
    'plan_id8'
)->build();

$subscriptionsController = $client->getSubscriptionsController();

try {
    $result = $subscriptionsController->createSubscription($body);
    echo 'CreateSubscriptionResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Search Subscriptions

Searches for subscriptions.
Results are ordered chronologically by subscription creation date. If
the request specifies more than one location ID,
the endpoint orders the result
by location ID, and then by creation date within each location. If no locations are given
in the query, all locations are searched.

You can also optionally specify `customer_ids` to search by customer.
If left unset, all customers
associated with the specified locations are returned.
If the request specifies customer IDs, the endpoint orders results
first by location, within location by customer ID, and within
customer by subscription creation date.

For more information, see
[Retrieve subscriptions](https://developer.squareup.com/docs/subscriptions-api/overview#retrieve-subscriptions).

```php
function searchSubscriptions(SearchSubscriptionsRequest $body): SearchSubscriptionsResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`SearchSubscriptionsRequest`](../../doc/models/search-subscriptions-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`SUBSCRIPTIONS_READ`

## Response Type

**200**: Success

[`SearchSubscriptionsResponse`](../../doc/models/search-subscriptions-response.md)

## Example Usage

```php
$body = SearchSubscriptionsRequestBuilder::init()->build();

$subscriptionsController = $client->getSubscriptionsController();

try {
    $result = $subscriptionsController->searchSubscriptions($body);
    echo 'SearchSubscriptionsResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Retrieve Subscription

Retrieves a subscription.

```php
function retrieveSubscription(string $subscriptionId): RetrieveSubscriptionResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `subscriptionId` | `string` | Template, Required | The ID of the subscription to retrieve. |

## Requires scope

### oauth2

`SUBSCRIPTIONS_READ`

## Response Type

**200**: Success

[`RetrieveSubscriptionResponse`](../../doc/models/retrieve-subscription-response.md)

## Example Usage

```php
$subscriptionId = 'subscription_id0';

$subscriptionsController = $client->getSubscriptionsController();

try {
    $result = $subscriptionsController->retrieveSubscription($subscriptionId);
    echo 'RetrieveSubscriptionResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Update Subscription

Updates a subscription. You can set, modify, and clear the
`subscription` field values.

```php
function updateSubscription(string $subscriptionId, UpdateSubscriptionRequest $body): UpdateSubscriptionResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `subscriptionId` | `string` | Template, Required | The ID for the subscription to update. |
| `body` | [`UpdateSubscriptionRequest`](../../doc/models/update-subscription-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`CUSTOMERS_READ`, `INVOICES_WRITE`, `ITEMS_READ`, `ORDERS_WRITE`, `PAYMENTS_WRITE`, `SUBSCRIPTIONS_WRITE`

## Response Type

**200**: Success

[`UpdateSubscriptionResponse`](../../doc/models/update-subscription-response.md)

## Example Usage

```php
$subscriptionId = 'subscription_id0';

$body = UpdateSubscriptionRequestBuilder::init()->build();

$subscriptionsController = $client->getSubscriptionsController();

try {
    $result = $subscriptionsController->updateSubscription(
        $subscriptionId,
        $body
    );
    echo 'UpdateSubscriptionResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Cancel Subscription

Sets the `canceled_date` field to the end of the active billing period.
After this date, the status changes from ACTIVE to CANCELED.

```php
function cancelSubscription(string $subscriptionId): CancelSubscriptionResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `subscriptionId` | `string` | Template, Required | The ID of the subscription to cancel. |

## Requires scope

### oauth2

`SUBSCRIPTIONS_WRITE`

## Response Type

**200**: Success

[`CancelSubscriptionResponse`](../../doc/models/cancel-subscription-response.md)

## Example Usage

```php
$subscriptionId = 'subscription_id0';

$subscriptionsController = $client->getSubscriptionsController();

try {
    $result = $subscriptionsController->cancelSubscription($subscriptionId);
    echo 'CancelSubscriptionResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# List Subscription Events

Lists all events for a specific subscription.
In the current implementation, only `START_SUBSCRIPTION` and `STOP_SUBSCRIPTION` (when the subscription was canceled) events are returned.

```php
function listSubscriptionEvents(
    string $subscriptionId,
    ?string $cursor = null,
    ?int $limit = null
): ListSubscriptionEventsResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `subscriptionId` | `string` | Template, Required | The ID of the subscription to retrieve the events for. |
| `cursor` | `?string` | Query, Optional | A pagination cursor returned by a previous call to this endpoint.<br>Provide this to retrieve the next set of results for the original query.<br><br>For more information, see [Pagination](https://developer.squareup.com/docs/working-with-apis/pagination). |
| `limit` | `?int` | Query, Optional | The upper limit on the number of subscription events to return<br>in the response.<br><br>Default: `200` |

## Requires scope

### oauth2

`SUBSCRIPTIONS_READ`

## Response Type

**200**: Success

[`ListSubscriptionEventsResponse`](../../doc/models/list-subscription-events-response.md)

## Example Usage

```php
$subscriptionId = 'subscription_id0';

$subscriptionsController = $client->getSubscriptionsController();

try {
    $result = $subscriptionsController->listSubscriptionEvents($subscriptionId);
    echo 'ListSubscriptionEventsResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Resume Subscription

Resumes a deactivated subscription.

```php
function resumeSubscription(string $subscriptionId): ResumeSubscriptionResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `subscriptionId` | `string` | Template, Required | The ID of the subscription to resume. |

## Requires scope

### oauth2

`CUSTOMERS_READ`, `INVOICES_WRITE`, `ITEMS_READ`, `ORDERS_WRITE`, `PAYMENTS_WRITE`, `SUBSCRIPTIONS_WRITE`

## Response Type

**200**: Success

[`ResumeSubscriptionResponse`](../../doc/models/resume-subscription-response.md)

## Example Usage

```php
$subscriptionId = 'subscription_id0';

$subscriptionsController = $client->getSubscriptionsController();

try {
    $result = $subscriptionsController->resumeSubscription($subscriptionId);
    echo 'ResumeSubscriptionResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

