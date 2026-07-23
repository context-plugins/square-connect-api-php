
# Invoice Payment Request

Represents a payment request for an [invoice](https://developer.squareup.com/reference/square_2021-08-18/objects/Invoice). Invoices can specify a maximum
of 13 payment requests, with up to 12 `INSTALLMENT` request types. For more information,
see [Payment requests](https://developer.squareup.com/docs/invoices-api/overview#payment-requests).

Adding `INSTALLMENT` payment requests to an invoice requires an
[Invoices Plus subscription](https://developer.squareup.com/docs/invoices-api/overview#invoices-plus-subscription).

## Structure

`InvoicePaymentRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `automaticPaymentSource` | `?string` | Optional | The payment method for an automatic payment.<br><br>The default value is `NONE`. | getAutomaticPaymentSource(): ?string | setAutomaticPaymentSource(?string automaticPaymentSource): void |
| `cardId` | `?string` | Optional | The ID of the credit or debit card on file to charge for the payment request. To get the cards on file for a customer,<br>call [ListCards](https://developer.squareup.com/reference/square_2021-08-18/cards-api/list-cards) and include the `customer_id` of the invoice recipient.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `255` | getCardId(): ?string | setCardId(?string cardId): void |
| `computedAmountMoney` | [`?Money`](../../doc/models/money.md) | Optional | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getComputedAmountMoney(): ?Money | setComputedAmountMoney(?Money computedAmountMoney): void |
| `dueDate` | `?string` | Optional | The due date (in the invoice's time zone) for the payment request, in `YYYY-MM-DD` format. This field<br>is required to create a payment request.<br><br>After this date, the invoice becomes overdue. For example, a payment `due_date` of 2021-03-09 with a `timezone`<br>of America/Los\_Angeles becomes overdue at midnight on March 9 in America/Los\_Angeles (which equals a UTC<br>timestamp of 2021-03-10T08:00:00Z). | getDueDate(): ?string | setDueDate(?string dueDate): void |
| `fixedAmountRequestedMoney` | [`?Money`](../../doc/models/money.md) | Optional | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getFixedAmountRequestedMoney(): ?Money | setFixedAmountRequestedMoney(?Money fixedAmountRequestedMoney): void |
| `percentageRequested` | `?string` | Optional | Specifies the amount for the payment request in percentage:<br><br>- When the payment `request_type` is `DEPOSIT`, it is the percentage of the order's total amount.<br>- When the payment `request_type` is `INSTALLMENT`, it is the percentage of the order's total less<br>  the deposit, if requested. The sum of the `percentage_requested` in all installment<br>  payment requests must be equal to 100.<br><br>You cannot specify this when the payment `request_type` is `BALANCE` or when the<br>payment request specifies the `fixed_amount_requested_money` field. | getPercentageRequested(): ?string | setPercentageRequested(?string percentageRequested): void |
| `reminders` | [`?(InvoicePaymentReminder[])`](../../doc/models/invoice-payment-reminder.md) | Optional | A list of one or more reminders to send for the payment request. | getReminders(): ?array | setReminders(?array reminders): void |
| `requestMethod` | `?string` | Optional | Indicates how Square processes the payment request. DEPRECATED at version 2021-01-21. Replaced by the<br>`Invoice.delivery_method` and `InvoicePaymentRequest.automatic_payment_source` fields.<br><br>One of the following is required when creating an invoice:<br><br>- (Recommended) The `delivery_method` field of the invoice. To configure an automatic payment, the<br>  `automatic_payment_source` field of the payment request is also required.<br>- This `request_method` field. Note that `invoice` objects returned in responses do not include `request_method`. | getRequestMethod(): ?string | setRequestMethod(?string requestMethod): void |
| `requestType` | `?string` | Optional | Identifies the payment request type. This type defines how the payment request amount is determined.<br>This field is required to create a payment request. | getRequestType(): ?string | setRequestType(?string requestType): void |
| `roundingAdjustmentIncludedMoney` | [`?Money`](../../doc/models/money.md) | Optional | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getRoundingAdjustmentIncludedMoney(): ?Money | setRoundingAdjustmentIncludedMoney(?Money roundingAdjustmentIncludedMoney): void |
| `tippingEnabled` | `?bool` | Optional | If set to true, the Square-hosted invoice page (the `public_url` field of the invoice)<br>provides a place for the customer to pay a tip.<br><br>This field is allowed only on the final payment request  <br>and the payment `request_type` must be `BALANCE` or `INSTALLMENT`. | getTippingEnabled(): ?bool | setTippingEnabled(?bool tippingEnabled): void |
| `totalCompletedAmountMoney` | [`?Money`](../../doc/models/money.md) | Optional | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getTotalCompletedAmountMoney(): ?Money | setTotalCompletedAmountMoney(?Money totalCompletedAmountMoney): void |
| `uid` | `?string` | Optional | The Square-generated ID of the payment request in an [invoice](https://developer.squareup.com/reference/square_2021-08-18/objects/Invoice).<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `255` | getUid(): ?string | setUid(?string uid): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\InvoicePaymentRequestBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;

$invoicePaymentRequest = InvoicePaymentRequestBuilder::init()
    ->automaticPaymentSource('automatic_payment_source6')
    ->cardId('card_id6')
    ->computedAmountMoney(
        MoneyBuilder::init()
            ->amount(32)
            ->currency('currency2')
            ->build()
    )
    ->dueDate('due_date6')
    ->fixedAmountRequestedMoney(
        MoneyBuilder::init()
            ->amount(162)
            ->currency('currency0')
            ->build()
    )
    ->build();
```

