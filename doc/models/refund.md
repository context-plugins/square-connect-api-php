
# Refund

Represents a refund processed for a Square transaction.

## Structure

`Refund`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `additionalRecipients` | [`?(AdditionalRecipient[])`](../../doc/models/additional-recipient.md) | Optional | Additional recipients (other than the merchant) receiving a portion of this refund.<br>For example, fees assessed on a refund of a purchase by a third party integration. | getAdditionalRecipients(): ?array | setAdditionalRecipients(?array additionalRecipients): void |
| `amountMoney` | [`Money`](../../doc/models/money.md) | Required | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getAmountMoney(): Money | setAmountMoney(Money amountMoney): void |
| `createdAt` | `?string` | Optional | The timestamp for when the refund was created, in RFC 3339 format.<br><br>**Constraints**: *Maximum Length*: `32` | getCreatedAt(): ?string | setCreatedAt(?string createdAt): void |
| `id` | `string` | Required | The refund's unique ID.<br><br>**Constraints**: *Maximum Length*: `255` | getId(): string | setId(string id): void |
| `locationId` | `string` | Required | The ID of the refund's associated location.<br><br>**Constraints**: *Maximum Length*: `50` | getLocationId(): string | setLocationId(string locationId): void |
| `processingFeeMoney` | [`?Money`](../../doc/models/money.md) | Optional | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getProcessingFeeMoney(): ?Money | setProcessingFeeMoney(?Money processingFeeMoney): void |
| `reason` | `string` | Required | The reason for the refund being issued.<br><br>**Constraints**: *Maximum Length*: `192` | getReason(): string | setReason(string reason): void |
| `status` | `string` | Required | The current status of the refund (`PENDING`, `APPROVED`, `REJECTED`,<br>or `FAILED`). | getStatus(): string | setStatus(string status): void |
| `tenderId` | `string` | Required | The ID of the refunded tender.<br><br>**Constraints**: *Maximum Length*: `192` | getTenderId(): string | setTenderId(string tenderId): void |
| `transactionId` | `string` | Required | The ID of the transaction that the refunded tender is part of.<br><br>**Constraints**: *Maximum Length*: `192` | getTransactionId(): string | setTransactionId(string transactionId): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\RefundBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;
use SquareConnectAPILib\Models\Builders\AdditionalRecipientBuilder;

$refund = RefundBuilder::init(
    MoneyBuilder::init()
        ->amount(186)
        ->currency('currency8')
        ->build(),
    'id8',
    'location_id2',
    'reason4',
    'status0',
    'tender_id6',
    'transaction_id6'
)
    ->additionalRecipients(
        [
            AdditionalRecipientBuilder::init(
                MoneyBuilder::init()
                    ->amount(186)
                    ->currency('currency8')
                    ->build(),
                'location_id0'
            )
                ->description('description6')
                ->receivableId('receivable_id6')
                ->build(),
            AdditionalRecipientBuilder::init(
                MoneyBuilder::init()
                    ->amount(186)
                    ->currency('currency8')
                    ->build(),
                'location_id0'
            )
                ->description('description6')
                ->receivableId('receivable_id6')
                ->build()
        ]
    )
    ->createdAt('created_at6')
    ->processingFeeMoney(
        MoneyBuilder::init()
            ->amount(112)
            ->currency('currency8')
            ->build()
    )
    ->build();
```

