
# Search Invoices Response

Describes a `SearchInvoices` response.

## Structure

`SearchInvoicesResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cursor` | `?string` | Optional | When a response is truncated, it includes a cursor that you can use in a<br>subsequent request to fetch the next set of invoices. If empty, this is the final<br>response.<br>For more information, see [Pagination](https://developer.squareup.com/docs/working-with-apis/pagination). | getCursor(): ?string | setCursor(?string cursor): void |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Information about errors encountered during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `invoices` | [`?(Invoice[])`](../../doc/models/invoice.md) | Optional | The list of invoices returned by the search. | getInvoices(): ?array | setInvoices(?array invoices): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\SearchInvoicesResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\InvoiceBuilder;
use SquareConnectAPILib\Models\Builders\InvoiceAcceptedPaymentMethodsBuilder;
use SquareConnectAPILib\Models\Builders\InvoiceCustomFieldBuilder;
use SquareConnectAPILib\ApiHelper;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;
use SquareConnectAPILib\Models\Builders\InvoicePaymentRequestBuilder;
use SquareConnectAPILib\Models\Builders\InvoicePaymentReminderBuilder;
use SquareConnectAPILib\Models\Builders\InvoiceRecipientBuilder;

$searchInvoicesResponse = SearchInvoicesResponseBuilder::init()
    ->cursor('ChoIDhIWVm54ZVRhLXhySFBOejBBM2xJb2daUQoFCI4IGAE')
    ->errors(
        [
            ErrorBuilder::init(
                'category8',
                'code8'
            )
                ->detail('detail6')
                ->field('field4')
                ->build()
        ]
    )
    ->invoices(
        [
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
                ->build(),
            InvoiceBuilder::init()
                ->acceptedPaymentMethods(
                    InvoiceAcceptedPaymentMethodsBuilder::init()
                        ->bankAccount(false)
                        ->card(true)
                        ->squareGiftCard(true)
                        ->build()
                )
                ->createdAt('2021-01-23T15:29:12Z')
                ->customFields(
                    [
                        InvoiceCustomFieldBuilder::init()
                            ->label('label2')
                            ->placement('placement6')
                            ->value('value4')
                            ->build()
                    ]
                )
                ->deliveryMethod(ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->description('description4')
                ->id('inv:0-ChC366qAfskpGrBI_1bozs9mEA3')
                ->invoiceNumber('inv-455')
                ->locationId('ES0RJRZYEC39A')
                ->nextPaymentAmountMoney(
                    MoneyBuilder::init()
                        ->amount(3000)
                        ->currency('USD')
                        ->build()
                )
                ->orderId('a65jnS8NXbfprvGJzY9F4fQTuaB')
                ->paymentRequests(
                    [
                        InvoicePaymentRequestBuilder::init()
                            ->automaticPaymentSource('CARD_ON_FILE')
                            ->cardId('ccof:IkWfpLj4tNHMyFii3GB')
                            ->computedAmountMoney(
                                MoneyBuilder::init()
                                    ->amount(1000)
                                    ->currency('USD')
                                    ->build()
                            )
                            ->dueDate('2021-01-23')
                            ->percentageRequested('25')
                            ->requestType('DEPOSIT')
                            ->tippingEnabled(false)
                            ->totalCompletedAmountMoney(
                                MoneyBuilder::init()
                                    ->amount(1000)
                                    ->currency('USD')
                                    ->build()
                            )
                            ->uid('66c3bdfd-5090-4ff9-a8a0-c1e1a2ffa176')
                            ->build(),
                        InvoicePaymentRequestBuilder::init()
                            ->automaticPaymentSource('CARD_ON_FILE')
                            ->cardId('ccof:IkWfpLj4tNHMyFii3GB')
                            ->computedAmountMoney(
                                MoneyBuilder::init()
                                    ->amount(3000)
                                    ->currency('USD')
                                    ->build()
                            )
                            ->dueDate('2021-06-15')
                            ->requestType('BALANCE')
                            ->tippingEnabled(false)
                            ->totalCompletedAmountMoney(
                                MoneyBuilder::init()
                                    ->amount(0)
                                    ->currency('USD')
                                    ->build()
                            )
                            ->uid('120c5e18-4f80-4f6b-b159-774cb9bf8f99')
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
                ->publicUrl('https://squareup.com/pay-invoice/h9sfsfTGTSnYEhISUDBhEQ')
                ->status('PARTIALLY_PAID')
                ->timezone('America/Los_Angeles')
                ->updatedAt('2021-01-23T15:29:56Z')
                ->version(3)
                ->build()
        ]
    )
    ->build();
```

