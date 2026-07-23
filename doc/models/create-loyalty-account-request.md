
# Create Loyalty Account Request

A request to create a new loyalty account.

## Structure

`CreateLoyaltyAccountRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `idempotencyKey` | `string` | Required | A unique string that identifies this `CreateLoyaltyAccount` request.<br>Keys can be any valid string, but must be unique for every request.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `128` | getIdempotencyKey(): string | setIdempotencyKey(string idempotencyKey): void |
| `loyaltyAccount` | [`LoyaltyAccount`](../../doc/models/loyalty-account.md) | Required | Describes a loyalty account. For more information, see<br>[Manage Loyalty Accounts Using the Loyalty API](https://developer.squareup.com/docs/loyalty-api/overview). | getLoyaltyAccount(): LoyaltyAccount | setLoyaltyAccount(LoyaltyAccount loyaltyAccount): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CreateLoyaltyAccountRequestBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyAccountBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyAccountExpiringPointDeadlineBuilder;

$createLoyaltyAccountRequest = CreateLoyaltyAccountRequestBuilder::init(
    'idempotency_key2',
    LoyaltyAccountBuilder::init(
        'program_id6'
    )
        ->balance(6)
        ->createdAt('created_at4')
        ->customerId('customer_id4')
        ->enrolledAt('enrolled_at6')
        ->expiringPointDeadlines(
            [
                LoyaltyAccountExpiringPointDeadlineBuilder::init(
                    'expires_at4',
                    218
                )->build(),
                LoyaltyAccountExpiringPointDeadlineBuilder::init(
                    'expires_at4',
                    218
                )->build(),
                LoyaltyAccountExpiringPointDeadlineBuilder::init(
                    'expires_at4',
                    218
                )->build()
            ]
        )->build()
)->build();
```

