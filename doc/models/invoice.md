
# Invoice

Stores information about an invoice. You use the Invoices API to create and manage
invoices. For more information, see [Manage Invoices Using the Invoices API](https://developer.squareup.com/docs/invoices-api/overview).

## Structure

`Invoice`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `acceptedPaymentMethods` | [`?InvoiceAcceptedPaymentMethods`](../../doc/models/invoice-accepted-payment-methods.md) | Optional | The payment methods that customers can use to pay an invoice on the Square-hosted invoice page. | getAcceptedPaymentMethods(): ?InvoiceAcceptedPaymentMethods | setAcceptedPaymentMethods(?InvoiceAcceptedPaymentMethods acceptedPaymentMethods): void |
| `createdAt` | `?string` | Optional | The timestamp when the invoice was created, in RFC 3339 format. | getCreatedAt(): ?string | setCreatedAt(?string createdAt): void |
| `customFields` | [`?(InvoiceCustomField[])`](../../doc/models/invoice-custom-field.md) | Optional | Additional seller-defined fields to render on the invoice. These fields are visible to sellers and buyers<br>on the Square-hosted invoice page and in emailed or PDF copies of invoices. For more information, see<br>[Custom fields](https://developer.squareup.com/docs/invoices-api/overview#custom-fields).<br><br>Adding custom fields to an invoice requires an<br>[Invoices Plus subscription](https://developer.squareup.com/docs/invoices-api/overview#invoices-plus-subscription).<br><br>Max: 2 custom fields | getCustomFields(): ?array | setCustomFields(?array customFields): void |
| `deliveryMethod` | `?array` | Optional | - | getDeliveryMethod(): ?array | setDeliveryMethod(?array deliveryMethod): void |
| `description` | `?string` | Optional | The description of the invoice. This is visible to the customer receiving the invoice.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `65536` | getDescription(): ?string | setDescription(?string description): void |
| `id` | `?string` | Optional | The Square-assigned ID of the invoice. | getId(): ?string | setId(?string id): void |
| `invoiceNumber` | `?string` | Optional | A user-friendly invoice number. The value is unique within a location.<br>If not provided when creating an invoice, Square assigns a value.<br>It increments from 1 and padded with zeros making it 7 characters long<br>(for example, 0000001 and 0000002).<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `191` | getInvoiceNumber(): ?string | setInvoiceNumber(?string invoiceNumber): void |
| `locationId` | `?string` | Optional | The ID of the location that this invoice is associated with.<br><br>If specified in a `CreateInvoice` request, the value must match the `location_id` of the associated order.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `255` | getLocationId(): ?string | setLocationId(?string locationId): void |
| `nextPaymentAmountMoney` | [`?Money`](../../doc/models/money.md) | Optional | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getNextPaymentAmountMoney(): ?Money | setNextPaymentAmountMoney(?Money nextPaymentAmountMoney): void |
| `orderId` | `?string` | Optional | The ID of the [order](https://developer.squareup.com/reference/square_2021-08-18/objects/Order) for which the invoice is created.<br>This field is required when creating an invoice, and the order must be in the `OPEN` state.<br><br>To view the line items and other information for the associated order, call the<br>[RetrieveOrder](https://developer.squareup.com/reference/square_2021-08-18/orders-api/retrieve-order) endpoint using the order ID.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `255` | getOrderId(): ?string | setOrderId(?string orderId): void |
| `paymentRequests` | [`?(InvoicePaymentRequest[])`](../../doc/models/invoice-payment-request.md) | Optional | The payment schedule for the invoice, represented by one or more payment requests that<br>define payment settings, such as amount due and due date. An invoice supports the following payment request combinations:<br><br>- One balance<br>- One deposit with one balance<br>- 2–12 installments<br>- One deposit with 2–12 installments<br><br>This field is required when creating an invoice. It must contain at least one payment request.<br>All payment requests for the invoice must equal the total order amount. For more information, see<br>[Payment requests](https://developer.squareup.com/docs/invoices-api/overview#payment-requests).<br><br>Adding `INSTALLMENT` payment requests to an invoice requires an<br>[Invoices Plus subscription](https://developer.squareup.com/docs/invoices-api/overview#invoices-plus-subscription). | getPaymentRequests(): ?array | setPaymentRequests(?array paymentRequests): void |
| `primaryRecipient` | [`?InvoiceRecipient`](../../doc/models/invoice-recipient.md) | Optional | Provides customer data that Square uses to deliver an invoice. | getPrimaryRecipient(): ?InvoiceRecipient | setPrimaryRecipient(?InvoiceRecipient primaryRecipient): void |
| `publicUrl` | `?string` | Optional | The URL of the Square-hosted invoice page.<br>After you publish the invoice using the `PublishInvoice` endpoint, Square hosts the invoice<br>page and returns the page URL in the response. | getPublicUrl(): ?string | setPublicUrl(?string publicUrl): void |
| `scheduledAt` | `?string` | Optional | The timestamp when the invoice is scheduled for processing, in RFC 3339 format.<br>After the invoice is published, Square processes the invoice on the specified date,<br>according to the delivery method and payment request settings.<br><br>If the field is not set, Square processes the invoice immediately after it is published. | getScheduledAt(): ?string | setScheduledAt(?string scheduledAt): void |
| `status` | `?string` | Optional | The status of the invoice. | getStatus(): ?string | setStatus(?string status): void |
| `subscriptionId` | `?string` | Optional | The ID of the [subscription](https://developer.squareup.com/reference/square_2021-08-18/objects/Subscription) associated with the invoice.<br>This field is present only on subscription billing invoices. | getSubscriptionId(): ?string | setSubscriptionId(?string subscriptionId): void |
| `timezone` | `?string` | Optional | The time zone used to interpret calendar dates on the invoice, such as `due_date`.<br>When an invoice is created, this field is set to the `timezone` specified for the seller<br>location. The value cannot be changed.<br><br>For example, a payment `due_date` of 2021-03-09 with a `timezone` of America/Los\_Angeles<br>becomes overdue at midnight on March 9 in America/Los\_Angeles (which equals a UTC timestamp<br>of 2021-03-10T08:00:00Z). | getTimezone(): ?string | setTimezone(?string timezone): void |
| `title` | `?string` | Optional | The title of the invoice.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `255` | getTitle(): ?string | setTitle(?string title): void |
| `updatedAt` | `?string` | Optional | The timestamp when the invoice was last updated, in RFC 3339 format. | getUpdatedAt(): ?string | setUpdatedAt(?string updatedAt): void |
| `version` | `?int` | Optional | The Square-assigned version number, which is incremented each time an update is committed to the invoice. | getVersion(): ?int | setVersion(?int version): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\InvoiceBuilder;
use SquareConnectAPILib\Models\Builders\InvoiceAcceptedPaymentMethodsBuilder;
use SquareConnectAPILib\Models\Builders\InvoiceCustomFieldBuilder;
use SquareConnectAPILib\ApiHelper;

$invoice = InvoiceBuilder::init()
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
    ->build();
```

