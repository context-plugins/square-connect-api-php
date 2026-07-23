# Invoices

```php
$invoicesController = $client->getInvoicesController();
```

## Class Name

`InvoicesController`

## Methods

* [List Invoices](../../doc/controllers/invoices.md#list-invoices)
* [Create Invoice](../../doc/controllers/invoices.md#create-invoice)
* [Search Invoices](../../doc/controllers/invoices.md#search-invoices)
* [Delete Invoice](../../doc/controllers/invoices.md#delete-invoice)
* [Get Invoice](../../doc/controllers/invoices.md#get-invoice)
* [Update Invoice](../../doc/controllers/invoices.md#update-invoice)
* [Cancel Invoice](../../doc/controllers/invoices.md#cancel-invoice)
* [Publish Invoice](../../doc/controllers/invoices.md#publish-invoice)


# List Invoices

Returns a list of invoices for a given location. The response
is paginated. If truncated, the response includes a `cursor` that you  
use in a subsequent request to retrieve the next set of invoices.

```php
function listInvoices(string $locationId, ?string $cursor = null, ?int $limit = null): ListInvoicesResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `locationId` | `string` | Query, Required | The ID of the location for which to list invoices. |
| `cursor` | `?string` | Query, Optional | A pagination cursor returned by a previous call to this endpoint.<br>Provide this cursor to retrieve the next set of results for your original query.<br><br>For more information, see [Pagination](https://developer.squareup.com/docs/working-with-apis/pagination). |
| `limit` | `?int` | Query, Optional | The maximum number of invoices to return (200 is the maximum `limit`).<br>If not provided, the server uses a default limit of 100 invoices. |

## Requires scope

### oauth2

`INVOICES_READ`

## Response Type

**200**: Success

[`ListInvoicesResponse`](../../doc/models/list-invoices-response.md)

## Example Usage

```php
$locationId = 'location_id4';

$invoicesController = $client->getInvoicesController();

try {
    $result = $invoicesController->listInvoices($locationId);
    echo 'ListInvoicesResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Create Invoice

Creates a draft [invoice](https://developer.squareup.com/reference/square_2021-08-18/objects/Invoice)
for an order created using the Orders API.

A draft invoice remains in your account and no action is taken.
You must publish the invoice before Square can process it (send it to the customer's email address or charge the customer’s card on file).

```php
function createInvoice(CreateInvoiceRequest $body): CreateInvoiceResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`CreateInvoiceRequest`](../../doc/models/create-invoice-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`INVOICES_WRITE`, `ORDERS_WRITE`

## Response Type

**200**: Success

[`CreateInvoiceResponse`](../../doc/models/create-invoice-response.md)

## Example Usage

```php
$body = CreateInvoiceRequestBuilder::init(
    InvoiceBuilder::init()->build()
)->build();

$invoicesController = $client->getInvoicesController();

try {
    $result = $invoicesController->createInvoice($body);
    echo 'CreateInvoiceResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Search Invoices

Searches for invoices from a location specified in
the filter. You can optionally specify customers in the filter for whom to
retrieve invoices. In the current implementation, you can only specify one location and
optionally one customer.

The response is paginated. If truncated, the response includes a `cursor`
that you use in a subsequent request to retrieve the next set of invoices.

```php
function searchInvoices(SearchInvoicesRequest $body): SearchInvoicesResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`SearchInvoicesRequest`](../../doc/models/search-invoices-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`INVOICES_READ`

## Response Type

**200**: Success

[`SearchInvoicesResponse`](../../doc/models/search-invoices-response.md)

## Example Usage

```php
$body = SearchInvoicesRequestBuilder::init(
    InvoiceQueryBuilder::init(
        InvoiceFilterBuilder::init(
            [
                'location_ids4'
            ]
        )->build()
    )->build()
)->build();

$invoicesController = $client->getInvoicesController();

try {
    $result = $invoicesController->searchInvoices($body);
    echo 'SearchInvoicesResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Delete Invoice

Deletes the specified invoice. When an invoice is deleted, the
associated order status changes to CANCELED. You can only delete a draft
invoice (you cannot delete a published invoice, including one that is scheduled for processing).

```php
function deleteInvoice(string $invoiceId, ?int $version = null): DeleteInvoiceResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `invoiceId` | `string` | Template, Required | The ID of the invoice to delete. |
| `version` | `?int` | Query, Optional | The version of the [invoice](https://developer.squareup.com/reference/square_2021-08-18/objects/Invoice) to delete.<br>If you do not know the version, you can call [GetInvoice](https://developer.squareup.com/reference/square_2021-08-18/invoices-api/get-invoice) or<br>[ListInvoices](https://developer.squareup.com/reference/square_2021-08-18/invoices-api/list-invoices). |

## Requires scope

### oauth2

`INVOICES_WRITE`, `ORDERS_WRITE`

## Response Type

**200**: Success

[`DeleteInvoiceResponse`](../../doc/models/delete-invoice-response.md)

## Example Usage

```php
$invoiceId = 'invoice_id0';

$invoicesController = $client->getInvoicesController();

try {
    $result = $invoicesController->deleteInvoice($invoiceId);
    echo 'DeleteInvoiceResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Get Invoice

Retrieves an invoice by invoice ID.

```php
function getInvoice(string $invoiceId): GetInvoiceResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `invoiceId` | `string` | Template, Required | The ID of the invoice to retrieve. |

## Requires scope

### oauth2

`INVOICES_READ`

## Response Type

**200**: Success

[`GetInvoiceResponse`](../../doc/models/get-invoice-response.md)

## Example Usage

```php
$invoiceId = 'invoice_id0';

$invoicesController = $client->getInvoicesController();

try {
    $result = $invoicesController->getInvoice($invoiceId);
    echo 'GetInvoiceResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Update Invoice

Updates an invoice by modifying fields, clearing fields, or both. For most updates, you can use a sparse
`Invoice` object to add fields or change values and use the `fields_to_clear` field to specify fields to clear.
However, some restrictions apply. For example, you cannot change the `order_id` or `location_id` field and you
must provide the complete `custom_fields` list to update a custom field. Published invoices have additional restrictions.

```php
function updateInvoice(string $invoiceId, UpdateInvoiceRequest $body): UpdateInvoiceResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `invoiceId` | `string` | Template, Required | The ID of the invoice to update. |
| `body` | [`UpdateInvoiceRequest`](../../doc/models/update-invoice-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`INVOICES_WRITE`, `ORDERS_WRITE`

## Response Type

**200**: Success

[`UpdateInvoiceResponse`](../../doc/models/update-invoice-response.md)

## Example Usage

```php
$invoiceId = 'invoice_id0';

$body = UpdateInvoiceRequestBuilder::init(
    InvoiceBuilder::init()->build()
)->build();

$invoicesController = $client->getInvoicesController();

try {
    $result = $invoicesController->updateInvoice(
        $invoiceId,
        $body
    );
    echo 'UpdateInvoiceResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Cancel Invoice

Cancels an invoice. The seller cannot collect payments for
the canceled invoice.

You cannot cancel an invoice in the `DRAFT` state or in a terminal state: `PAID`, `REFUNDED`, `CANCELED`, or `FAILED`.

```php
function cancelInvoice(string $invoiceId, CancelInvoiceRequest $body): CancelInvoiceResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `invoiceId` | `string` | Template, Required | The ID of the [invoice](https://developer.squareup.com/reference/square_2021-08-18/objects/Invoice) to cancel. |
| `body` | [`CancelInvoiceRequest`](../../doc/models/cancel-invoice-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`INVOICES_WRITE`, `ORDERS_WRITE`

## Response Type

**200**: Success

[`CancelInvoiceResponse`](../../doc/models/cancel-invoice-response.md)

## Example Usage

```php
$invoiceId = 'invoice_id0';

$body = CancelInvoiceRequestBuilder::init(
    92
)->build();

$invoicesController = $client->getInvoicesController();

try {
    $result = $invoicesController->cancelInvoice(
        $invoiceId,
        $body
    );
    echo 'CancelInvoiceResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Publish Invoice

Publishes the specified draft invoice.

After an invoice is published, Square
follows up based on the invoice configuration. For example, Square
sends the invoice to the customer's email address, charges the customer's card on file, or does
nothing. Square also makes the invoice available on a Square-hosted invoice page.

The invoice `status` also changes from `DRAFT` to a status
based on the invoice configuration. For example, the status changes to `UNPAID` if
Square emails the invoice or `PARTIALLY_PAID` if Square charge a card on file for a portion of the
invoice amount.

```php
function publishInvoice(string $invoiceId, PublishInvoiceRequest $body): PublishInvoiceResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `invoiceId` | `string` | Template, Required | The ID of the invoice to publish. |
| `body` | [`PublishInvoiceRequest`](../../doc/models/publish-invoice-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`INVOICES_WRITE`, `ORDERS_WRITE`

## Response Type

**200**: Success

[`PublishInvoiceResponse`](../../doc/models/publish-invoice-response.md)

## Example Usage

```php
$invoiceId = 'invoice_id0';

$body = PublishInvoiceRequestBuilder::init(
    92
)->build();

$invoicesController = $client->getInvoicesController();

try {
    $result = $invoicesController->publishInvoice(
        $invoiceId,
        $body
    );
    echo 'PublishInvoiceResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

