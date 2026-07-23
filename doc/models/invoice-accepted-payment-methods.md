
# Invoice Accepted Payment Methods

The payment methods that customers can use to pay an invoice on the Square-hosted invoice page.

## Structure

`InvoiceAcceptedPaymentMethods`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `bankAccount` | `?bool` | Optional | Indicates whether bank transfer payments are accepted. The default value is `false`.<br><br>This option is allowed only for invoices that have a single payment request of type `BALANCE`. | getBankAccount(): ?bool | setBankAccount(?bool bankAccount): void |
| `card` | `?bool` | Optional | Indicates whether credit card or debit card payments are accepted. The default value is `false`. | getCard(): ?bool | setCard(?bool card): void |
| `squareGiftCard` | `?bool` | Optional | Indicates whether Square gift card payments are accepted. The default value is `false`. | getSquareGiftCard(): ?bool | setSquareGiftCard(?bool squareGiftCard): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\InvoiceAcceptedPaymentMethodsBuilder;

$invoiceAcceptedPaymentMethods = InvoiceAcceptedPaymentMethodsBuilder::init()
    ->bankAccount(false)
    ->card(false)
    ->squareGiftCard(false)
    ->build();
```

