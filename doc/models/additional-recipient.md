
# Additional Recipient

Represents an additional recipient (other than the merchant) receiving a portion of this tender.

## Structure

`AdditionalRecipient`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amountMoney` | [`Money`](../../doc/models/money.md) | Required | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getAmountMoney(): Money | setAmountMoney(Money amountMoney): void |
| `description` | `?string` | Optional | The description of the additional recipient.<br><br>**Constraints**: *Maximum Length*: `100` | getDescription(): ?string | setDescription(?string description): void |
| `locationId` | `string` | Required | The location ID for a recipient (other than the merchant) receiving a portion of this tender.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `50` | getLocationId(): string | setLocationId(string locationId): void |
| `receivableId` | `?string` | Optional | The unique ID for this [AdditionalRecipientReceivable](https://developer.squareup.com/reference/square_2021-08-18/objects/AdditionalRecipientReceivable), assigned by the server.<br><br>**Constraints**: *Maximum Length*: `192` | getReceivableId(): ?string | setReceivableId(?string receivableId): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\AdditionalRecipientBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;

$additionalRecipient = AdditionalRecipientBuilder::init(
    MoneyBuilder::init()
        ->amount(186)
        ->currency('currency8')
        ->build(),
    'location_id8'
)
    ->description('description4')
    ->receivableId('receivable_id4')
    ->build();
```

