
# Dispute Evidence Created Webhook

Published when evidence is added to a [Dispute](https://developer.squareup.com/reference/square_2021-08-18/objects/Dispute)
from the Disputes Dashboard in the Seller Dashboard, the Square Point of Sale app,
or by calling either [CreateDisputeEvidenceFile](https://developer.squareup.com/reference/square_2021-08-18/disputes-api/create-dispute-evidence-file) or [CreateDisputeEvidenceText](https://developer.squareup.com/reference/square_2021-08-18/disputes-api/create-dispute-evidence-text).

## Structure

`DisputeEvidenceCreatedWebhook`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `createdAt` | `?string` | Optional | Timestamp of when the webhook event was created, in RFC 3339 format. | getCreatedAt(): ?string | setCreatedAt(?string createdAt): void |
| `data` | [`?DisputeEvidenceCreatedWebhookData`](../../doc/models/dispute-evidence-created-webhook-data.md) | Optional | - | getData(): ?DisputeEvidenceCreatedWebhookData | setData(?DisputeEvidenceCreatedWebhookData data): void |
| `eventId` | `?string` | Optional | A unique ID for the webhook event. | getEventId(): ?string | setEventId(?string eventId): void |
| `locationId` | `?string` | Optional | The ID of the target location associated with the event. | getLocationId(): ?string | setLocationId(?string locationId): void |
| `merchantId` | `?string` | Optional | The ID of the target merchant associated with the event. | getMerchantId(): ?string | setMerchantId(?string merchantId): void |
| `type` | `?string` | Optional | The type of event this represents. | getType(): ?string | setType(?string type): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\DisputeEvidenceCreatedWebhookBuilder;
use SquareConnectAPILib\Models\Builders\DisputeEvidenceCreatedWebhookDataBuilder;
use SquareConnectAPILib\Models\Builders\DisputeEvidenceCreatedWebhookObjectBuilder;
use SquareConnectAPILib\Models\Builders\DisputeBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;

$disputeEvidenceCreatedWebhook = DisputeEvidenceCreatedWebhookBuilder::init()
    ->createdAt('2020-02-19T21:27:28.851Z')
    ->data(
        DisputeEvidenceCreatedWebhookDataBuilder::init()
            ->id('ORSEVtZAJxb37RA1EiGw')
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
            ->type('dispute')
            ->build()
    )
    ->eventId('6f606f30-53d0-495a-87f0-958576fc954f')
    ->locationId('VJDQQP3CG14EY')
    ->merchantId('0HPGX5JYE6EE1')
    ->type('dispute.evidence.created')
    ->build();
```

