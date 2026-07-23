
# Invoice Payment Reminder

Describes a payment request reminder (automatic notification) that Square sends
to the customer. You configure a reminder relative to the payment request
`due_date`.

## Structure

`InvoicePaymentReminder`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `message` | `?string` | Optional | The reminder message.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `1000` | getMessage(): ?string | setMessage(?string message): void |
| `relativeScheduledDays` | `?int` | Optional | The number of days before (a negative number) or after (a positive number)<br>the payment request `due_date` when the reminder is sent. For example, -3 indicates that<br>the reminder should be sent 3 days before the payment request `due_date`.<br><br>**Constraints**: `>= -32767`, `<= 32767` | getRelativeScheduledDays(): ?int | setRelativeScheduledDays(?int relativeScheduledDays): void |
| `sentAt` | `?string` | Optional | If sent, the timestamp when the reminder was sent, in RFC 3339 format. | getSentAt(): ?string | setSentAt(?string sentAt): void |
| `status` | `?string` | Optional | The status of the reminder. | getStatus(): ?string | setStatus(?string status): void |
| `uid` | `?string` | Optional | A Square-assigned ID that uniquely identifies the reminder within the<br>`InvoicePaymentRequest`. | getUid(): ?string | setUid(?string uid): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\InvoicePaymentReminderBuilder;

$invoicePaymentReminder = InvoicePaymentReminderBuilder::init()
    ->message('message6')
    ->relativeScheduledDays(152)
    ->sentAt('sent_at6')
    ->status('status2')
    ->uid('uid6')
    ->build();
```

