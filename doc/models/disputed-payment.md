
# Disputed Payment

The payment the cardholder disputed.

## Structure

`DisputedPayment`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `paymentId` | `?string` | Optional | Square-generated unique ID of the payment being disputed.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `192` | getPaymentId(): ?string | setPaymentId(?string paymentId): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\DisputedPaymentBuilder;

$disputedPayment = DisputedPaymentBuilder::init()
    ->paymentId('payment_id2')
    ->build();
```

