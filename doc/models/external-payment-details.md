
# External Payment Details

Stores details about an external payment. Contains only non-confidential information.
For more information, see
[Take External Payments](https://developer.squareup.com/docs/payments-api/take-payments/external-payments).

## Structure

`ExternalPaymentDetails`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `source` | `string` | Required | A description of the external payment source. For example,<br>"Food Delivery Service".<br><br>**Constraints**: *Maximum Length*: `255` | getSource(): string | setSource(string source): void |
| `sourceFeeMoney` | [`?Money`](../../doc/models/money.md) | Optional | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getSourceFeeMoney(): ?Money | setSourceFeeMoney(?Money sourceFeeMoney): void |
| `sourceId` | `?string` | Optional | An ID to associate the payment to its originating source.<br><br>**Constraints**: *Maximum Length*: `255` | getSourceId(): ?string | setSourceId(?string sourceId): void |
| `type` | `string` | Required | The type of external payment the seller received. It can be one of the following:<br><br>- CHECK - Paid using a physical check.<br>- BANK_TRANSFER - Paid using external bank transfer.<br>- OTHER\_GIFT\_CARD - Paid using a non-Square gift card.<br>- CRYPTO - Paid using a crypto currency.<br>- SQUARE_CASH - Paid using Square Cash App.<br>- SOCIAL - Paid using peer-to-peer payment applications.<br>- EXTERNAL - A third-party application gathered this payment outside of Square.<br>- EMONEY - Paid using an E-money provider.<br>- CARD - A credit or debit card that Square does not support.<br>- STORED_BALANCE - Use for house accounts, store credit, and so forth.<br>- FOOD_VOUCHER - Restaurant voucher provided by employers to employees to pay for meals<br>- OTHER - A type not listed here.<br><br>**Constraints**: *Maximum Length*: `50` | getType(): string | setType(string type): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\ExternalPaymentDetailsBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;

$externalPaymentDetails = ExternalPaymentDetailsBuilder::init(
    'source4',
    'type0'
)
    ->sourceFeeMoney(
        MoneyBuilder::init()
            ->amount(130)
            ->currency('currency4')
            ->build()
    )
    ->sourceId('source_id6')
    ->build();
```

