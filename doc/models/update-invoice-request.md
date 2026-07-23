
# Update Invoice Request

Describes a `UpdateInvoice` request.

## Structure

`UpdateInvoiceRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `fieldsToClear` | `?(string[])` | Optional | The list of fields to clear.<br>For examples, see [Update an invoice](https://developer.squareup.com/docs/invoices-api/overview#update-an-invoice). | getFieldsToClear(): ?array | setFieldsToClear(?array fieldsToClear): void |
| `idempotencyKey` | `?string` | Optional | A unique string that identifies the `UpdateInvoice` request. If you do not<br>provide `idempotency_key` (or provide an empty string as the value), the endpoint<br>treats each request as independent.<br><br>For more information, see [Idempotency](https://developer.squareup.com/docs/working-with-apis/idempotency).<br><br>**Constraints**: *Maximum Length*: `128` | getIdempotencyKey(): ?string | setIdempotencyKey(?string idempotencyKey): void |
| `invoice` | [`Invoice`](../../doc/models/invoice.md) | Required | Stores information about an invoice. You use the Invoices API to create and manage<br>invoices. For more information, see [Manage Invoices Using the Invoices API](https://developer.squareup.com/docs/invoices-api/overview). | getInvoice(): Invoice | setInvoice(Invoice invoice): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\UpdateInvoiceRequestBuilder;
use SquareConnectAPILib\Models\Builders\InvoiceBuilder;
use SquareConnectAPILib\Models\Builders\InvoiceAcceptedPaymentMethodsBuilder;
use SquareConnectAPILib\Models\Builders\InvoiceCustomFieldBuilder;
use SquareConnectAPILib\ApiHelper;

$updateInvoiceRequest = UpdateInvoiceRequestBuilder::init(
    InvoiceBuilder::init()
        ->acceptedPaymentMethods(
            InvoiceAcceptedPaymentMethodsBuilder::init()
                ->bankAccount(false)
                ->card(false)
                ->squareGiftCard(false)
                ->build()
        )
        ->createdAt('created_at6')
        ->customFields(
            [
                InvoiceCustomFieldBuilder::init()
                    ->label('label2')
                    ->placement('placement6')
                    ->value('value4')
                    ->build(),
                InvoiceCustomFieldBuilder::init()
                    ->label('label2')
                    ->placement('placement6')
                    ->value('value4')
                    ->build(),
                InvoiceCustomFieldBuilder::init()
                    ->label('label2')
                    ->placement('placement6')
                    ->value('value4')
                    ->build()
            ]
        )
        ->deliveryMethod(ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
        ->description('description4')
        ->build()
)
    ->fieldsToClear(
        [
            'fields_to_clear3',
            'fields_to_clear4'
        ]
    )
    ->idempotencyKey('idempotency_key8')
    ->build();
```

