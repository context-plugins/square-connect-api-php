
# Cancel Invoice Request

Describes a `CancelInvoice` request.

## Structure

`CancelInvoiceRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `version` | `int` | Required | The version of the [invoice](https://developer.squareup.com/reference/square_2021-08-18/objects/Invoice) to cancel.<br>If you do not know the version, you can call<br>[GetInvoice](https://developer.squareup.com/reference/square_2021-08-18/invoices-api/get-invoice) or [ListInvoices](https://developer.squareup.com/reference/square_2021-08-18/invoices-api/list-invoices). | getVersion(): int | setVersion(int version): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CancelInvoiceRequestBuilder;

$cancelInvoiceRequest = CancelInvoiceRequestBuilder::init(
    152
)->build();
```

