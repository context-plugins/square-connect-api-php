
# Delete Invoice Request

Describes a `DeleteInvoice` request.

## Structure

`DeleteInvoiceRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `version` | `?int` | Optional | The version of the [invoice](https://developer.squareup.com/reference/square_2021-08-18/objects/Invoice) to delete.<br>If you do not know the version, you can call [GetInvoice](https://developer.squareup.com/reference/square_2021-08-18/invoices-api/get-invoice) or<br>[ListInvoices](https://developer.squareup.com/reference/square_2021-08-18/invoices-api/list-invoices). | getVersion(): ?int | setVersion(?int version): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\DeleteInvoiceRequestBuilder;

$deleteInvoiceRequest = DeleteInvoiceRequestBuilder::init()
    ->version(76)
    ->build();
```

