
# Create Gift Card Request

A request to create a gift card.

## Structure

`CreateGiftCardRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `giftCard` | [`GiftCard`](../../doc/models/gift-card.md) | Required | Represents a Square gift card. | getGiftCard(): GiftCard | setGiftCard(GiftCard giftCard): void |
| `idempotencyKey` | `string` | Required | A unique string that identifies the `CreateGiftCard` request.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `128` | getIdempotencyKey(): string | setIdempotencyKey(string idempotencyKey): void |
| `locationId` | `string` | Required | The location ID where the gift card that will be created should be registered.<br><br>**Constraints**: *Minimum Length*: `1` | getLocationId(): string | setLocationId(string locationId): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CreateGiftCardRequestBuilder;
use SquareConnectAPILib\Models\Builders\GiftCardBuilder;
use SquareConnectAPILib\ApiHelper;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;

$createGiftCardRequest = CreateGiftCardRequestBuilder::init(
    GiftCardBuilder::init(
        ApiHelper::deserialize('{"key1":"val1","key2":"val2"}')
    )
        ->balanceMoney(
            MoneyBuilder::init()
                ->amount(146)
                ->currency('currency6')
                ->build()
        )
        ->createdAt('created_at8')
        ->customerIds(
            [
                'customer_ids1'
            ]
        )
        ->gan('gan6')
        ->ganSource(ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
        ->build(),
    'idempotency_key0',
    'location_id8'
)->build();
```

