
# Gift Card Activity Redeem

Present only when `GiftCardActivityType` is REDEEM.

## Structure

`GiftCardActivityRedeem`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amountMoney` | [`Money`](../../doc/models/money.md) | Required | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getAmountMoney(): Money | setAmountMoney(Money amountMoney): void |
| `paymentId` | `?string` | Optional | When the Square Payments API is used, Redeem is not called on the Gift Cards API.<br>However, when Square reads a Redeem activity from the Gift Cards API, developers need to know the<br>associated `payment_id`. | getPaymentId(): ?string | setPaymentId(?string paymentId): void |
| `referenceId` | `?string` | Optional | A client-specified ID to associate an entity, in another system, with this gift card<br>activity. This can be used to track the order or payment related information when the Square Orders<br>API is not being used. | getReferenceId(): ?string | setReferenceId(?string referenceId): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\GiftCardActivityRedeemBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;

$giftCardActivityRedeem = GiftCardActivityRedeemBuilder::init(
    MoneyBuilder::init()
        ->amount(186)
        ->currency('currency8')
        ->build()
)
    ->paymentId('payment_id4')
    ->referenceId('reference_id2')
    ->build();
```

