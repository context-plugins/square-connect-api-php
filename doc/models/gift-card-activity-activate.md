
# Gift Card Activity Activate

Describes a gift card activity of the ACTIVATE type.

## Structure

`GiftCardActivityActivate`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amountMoney` | [`?Money`](../../doc/models/money.md) | Optional | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getAmountMoney(): ?Money | setAmountMoney(?Money amountMoney): void |
| `buyerPaymentInstrumentIds` | `?(string[])` | Optional | Required if your application does not use the Square Orders API.<br>This is a list of client-provided payment instrument IDs.<br>Square uses this information to perform compliance checks.<br>If you use the Square Orders API, Square has the necessary instrument IDs to perform necessary<br>compliance checks. | getBuyerPaymentInstrumentIds(): ?array | setBuyerPaymentInstrumentIds(?array buyerPaymentInstrumentIds): void |
| `lineItemUid` | `?string` | Optional | The `line_item_uid` of the gift card line item in an order.<br>This is required if your application uses the Square Orders API. | getLineItemUid(): ?string | setLineItemUid(?string lineItemUid): void |
| `orderId` | `?string` | Optional | The ID of the order associated with the activity.<br>This is required if your application uses the Square Orders API. | getOrderId(): ?string | setOrderId(?string orderId): void |
| `referenceId` | `?string` | Optional | If your application does not use the Square Orders API, you can optionally use this field<br>to associate the gift card activity with a client-side entity. | getReferenceId(): ?string | setReferenceId(?string referenceId): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\GiftCardActivityActivateBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;

$giftCardActivityActivate = GiftCardActivityActivateBuilder::init()
    ->amountMoney(
        MoneyBuilder::init()
            ->amount(186)
            ->currency('currency8')
            ->build()
    )
    ->buyerPaymentInstrumentIds(
        [
            'buyer_payment_instrument_ids0',
            'buyer_payment_instrument_ids1'
        ]
    )
    ->lineItemUid('line_item_uid4')
    ->orderId('order_id8')
    ->referenceId('reference_id2')
    ->build();
```

