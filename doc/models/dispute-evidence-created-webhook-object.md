
# Dispute Evidence Created Webhook Object

## Structure

`DisputeEvidenceCreatedWebhookObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `object` | [`?Dispute`](../../doc/models/dispute.md) | Optional | Represents a dispute a cardholder initiated with their bank. | getObject(): ?Dispute | setObject(?Dispute object): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\DisputeEvidenceCreatedWebhookObjectBuilder;
use SquareConnectAPILib\Models\Builders\DisputeBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;

$disputeEvidenceCreatedWebhookObject = DisputeEvidenceCreatedWebhookObjectBuilder::init()
    ->object(
        DisputeBuilder::init()
            ->amountMoney(
                MoneyBuilder::init()
                    ->amount(186)
                    ->currency('currency8')
                    ->build()
            )
            ->brandDisputeId('brand_dispute_id2')
            ->cardBrand('card_brand4')
            ->createdAt('created_at0')
            ->disputeId('dispute_id4')
            ->build()
    )
    ->build();
```

