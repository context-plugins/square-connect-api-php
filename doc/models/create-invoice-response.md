
# Create Invoice Response

The response returned by the `CreateInvoice` request.

## Structure

`CreateInvoiceResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Information about errors encountered during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `invoice` | [`?Invoice`](../../doc/models/invoice.md) | Optional | Stores information about an invoice. You use the Invoices API to create and manage<br>invoices. For more information, see [Manage Invoices Using the Invoices API](https://developer.squareup.com/docs/invoices-api/overview). | getInvoice(): ?Invoice | setInvoice(?Invoice invoice): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CreateInvoiceResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\InvoiceBuilder;
use SquareConnectAPILib\Models\Builders\InvoiceAcceptedPaymentMethodsBuilder;
use SquareConnectAPILib\Models\Builders\InvoiceCustomFieldBuilder;
use SquareConnectAPILib\ApiHelper;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;
use SquareConnectAPILib\Models\Builders\InvoicePaymentRequestBuilder;
use SquareConnectAPILib\Models\Builders\InvoicePaymentReminderBuilder;
use SquareConnectAPILib\Models\Builders\InvoiceRecipientBuilder;

$createInvoiceResponse = CreateInvoiceResponseBuilder::init()
    ->errors(
        [
            ErrorBuilder::init(
                'category8',
                'code8'
            )
                ->detail('detail6')
                ->field('field4')
                ->build(),
            ErrorBuilder::init(
                'category8',
                'code8'
            )
                ->detail('detail6')
                ->field('field4')
                ->build(),
            ErrorBuilder::init(
                'category8',
                'code8'
            )
                ->detail('detail6')
                ->field('field4')
                ->build()
        ]
    )
    ->invoice(
        InvoiceBuilder::init()
            ->acceptedPaymentMethods(
                InvoiceAcceptedPaymentMethodsBuilder::init()
                    ->bankAccount(false)
                    ->card(true)
                    ->squareGiftCard(false)
                    ->build()
            )
            ->createdAt('2020-06-18T17:45:13Z')
            ->customFields(
                [
                    InvoiceCustomFieldBuilder::init()
                        ->label('Event Reference Number')
                        ->placement('ABOVE_LINE_ITEMS')
                        ->value('Ref. #1234')
                        ->build(),
                    InvoiceCustomFieldBuilder::init()
                        ->label('Terms of Service')
                        ->placement('BELOW_LINE_ITEMS')
                        ->value('The terms of service are...')
                        ->build()
                ]
            )
            ->deliveryMethod(ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->description('We appreciate your business!')
            ->id('inv:0-ChCHu2mZEabLeeHahQnXDjZQECY')
            ->invoiceNumber('inv-100')
            ->locationId('ES0RJRZYEC39A')
            ->orderId('CAISENgvlJ6jLWAzERDzjyHVybY')
            ->paymentRequests(
                [
                    InvoicePaymentRequestBuilder::init()
                        ->automaticPaymentSource('NONE')
                        ->computedAmountMoney(
                            MoneyBuilder::init()
                                ->amount(10000)
                                ->currency('USD')
                                ->build()
                        )
                        ->dueDate('2030-01-24')
                        ->reminders(
                            [
                                InvoicePaymentReminderBuilder::init()
                                    ->message('Your invoice is due tomorrow')
                                    ->relativeScheduledDays(-1)
                                    ->status('PENDING')
                                    ->uid('beebd363-e47f-4075-8785-c235aaa7df11')
                                    ->build()
                            ]
                        )
                        ->requestType('BALANCE')
                        ->tippingEnabled(true)
                        ->totalCompletedAmountMoney(
                            MoneyBuilder::init()
                                ->amount(0)
                                ->currency('USD')
                                ->build()
                        )
                        ->uid('2da7964f-f3d2-4f43-81e8-5aa220bf3355')
                        ->build()
                ]
            )
            ->primaryRecipient(
                InvoiceRecipientBuilder::init()
                    ->customerId('JDKYHBWT1D4F8MFH63DBMEN8Y4')
                    ->emailAddress('Amelia.Earhart@example.com')
                    ->familyName('Earhart')
                    ->givenName('Amelia')
                    ->phoneNumber('1-212-555-4240')
                    ->build()
            )
            ->scheduledAt('2030-01-13T10:00:00Z')
            ->status('DRAFT')
            ->timezone('America/Los_Angeles')
            ->title('Event Planning Services')
            ->updatedAt('2020-06-18T17:45:13Z')
            ->version(0)
            ->build()
    )
    ->build();
```

