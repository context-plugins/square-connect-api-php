
# Dispute Evidence Created Webhook Data

## Structure

`DisputeEvidenceCreatedWebhookData`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | ID of the affected dispute. | getId(): ?string | setId(?string id): void |
| `object` | [`?DisputeEvidenceCreatedWebhookObject`](../../doc/models/dispute-evidence-created-webhook-object.md) | Optional | - | getObject(): ?DisputeEvidenceCreatedWebhookObject | setObject(?DisputeEvidenceCreatedWebhookObject object): void |
| `type` | `?string` | Optional | Name of the affected dispute's type. | getType(): ?string | setType(?string type): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\DisputeEvidenceCreatedWebhookDataBuilder;
use SquareConnectAPILib\Models\Builders\DisputeEvidenceCreatedWebhookObjectBuilder;
use SquareConnectAPILib\Models\Builders\DisputeBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;

$disputeEvidenceCreatedWebhookData = DisputeEvidenceCreatedWebhookDataBuilder::init()
    ->id('id6')
    ->object(
        DisputeEvidenceCreatedWebhookObjectBuilder::init()
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
            ->build()
    )
    ->type('type4')
    ->build();
```

