
# Create Refund Request

Defines the body parameters that can be included in
a request to the [CreateRefund](https://developer.squareup.com/reference/square_2021-08-18/transactions-api/create-refund) endpoint.

Deprecated - recommend using [RefundPayment](https://developer.squareup.com/reference/square_2021-08-18/refunds-api/refund-payment)

## Structure

`CreateRefundRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amountMoney` | [`Money`](../../doc/models/money.md) | Required | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getAmountMoney(): Money | setAmountMoney(Money amountMoney): void |
| `idempotencyKey` | `string` | Required | A value you specify that uniquely identifies this<br>refund among refunds you've created for the tender.<br><br>If you're unsure whether a particular refund succeeded,<br>you can reattempt it with the same idempotency key without<br>worrying about duplicating the refund.<br><br>See [Idempotency keys](https://developer.squareup.com/docs/working-with-apis/idempotency) for more information.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `192` | getIdempotencyKey(): string | setIdempotencyKey(string idempotencyKey): void |
| `reason` | `?string` | Optional | A description of the reason for the refund.<br><br>Default value: `Refund via API`<br><br>**Constraints**: *Maximum Length*: `192` | getReason(): ?string | setReason(?string reason): void |
| `tenderId` | `string` | Required | The ID of the tender to refund.<br><br>A [`Transaction`](https://developer.squareup.com/reference/square_2021-08-18/objects/Transaction) has one or more `tenders` (i.e., methods<br>of payment) associated with it, and you refund each tender separately with<br>the Connect API.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `192` | getTenderId(): string | setTenderId(string tenderId): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CreateRefundRequestBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;

$createRefundRequest = CreateRefundRequestBuilder::init(
    MoneyBuilder::init()
        ->amount(186)
        ->currency('currency8')
        ->build(),
    'idempotency_key6',
    'tender_id8'
)
    ->reason('reason6')
    ->build();
```

