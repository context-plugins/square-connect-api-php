
# Loyalty Account

Describes a loyalty account. For more information, see
[Manage Loyalty Accounts Using the Loyalty API](https://developer.squareup.com/docs/loyalty-api/overview).

## Structure

`LoyaltyAccount`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `balance` | `?int` | Optional | The available point balance in the loyalty account. If points are scheduled to expire, they are listed in the `expiring_point_deadlines` field.<br><br>Your application should be able to handle loyalty accounts that have a negative point balance (`balance` is less than 0). This might occur if a seller makes a manual adjustment or as a result of a refund or exchange. | getBalance(): ?int | setBalance(?int balance): void |
| `createdAt` | `?string` | Optional | The timestamp when the loyalty account was created, in RFC 3339 format. | getCreatedAt(): ?string | setCreatedAt(?string createdAt): void |
| `customerId` | `?string` | Optional | The Square-assigned ID of the [customer](https://developer.squareup.com/reference/square_2021-08-18/objects/Customer) that is associated with the account. | getCustomerId(): ?string | setCustomerId(?string customerId): void |
| `enrolledAt` | `?string` | Optional | The timestamp when enrollment occurred, in RFC 3339 format. | getEnrolledAt(): ?string | setEnrolledAt(?string enrolledAt): void |
| `expiringPointDeadlines` | [`?(LoyaltyAccountExpiringPointDeadline[])`](../../doc/models/loyalty-account-expiring-point-deadline.md) | Optional | The schedule for when points expire in the loyalty account balance. This field is present only if the account has points that are scheduled to expire.<br><br>The total number of points in this field equals the number of points in the `balance` field. | getExpiringPointDeadlines(): ?array | setExpiringPointDeadlines(?array expiringPointDeadlines): void |
| `id` | `?string` | Optional | The Square-assigned ID of the loyalty account.<br><br>**Constraints**: *Maximum Length*: `36` | getId(): ?string | setId(?string id): void |
| `lifetimePoints` | `?int` | Optional | The total points accrued during the lifetime of the account.<br><br>**Constraints**: `>= 0` | getLifetimePoints(): ?int | setLifetimePoints(?int lifetimePoints): void |
| `mapping` | [`?LoyaltyAccountMapping`](../../doc/models/loyalty-account-mapping.md) | Optional | Represents the mapping that associates a loyalty account with a buyer.<br><br>Currently, a loyalty account can only be mapped to a buyer by phone number. For more information, see<br>[Loyalty Overview](https://developer.squareup.com/docs/loyalty/overview). | getMapping(): ?LoyaltyAccountMapping | setMapping(?LoyaltyAccountMapping mapping): void |
| `programId` | `string` | Required | The Square-assigned ID of the [loyalty program](https://developer.squareup.com/reference/square_2021-08-18/objects/LoyaltyProgram) to which the account belongs.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `36` | getProgramId(): string | setProgramId(string programId): void |
| `updatedAt` | `?string` | Optional | The timestamp when the loyalty account was last updated, in RFC 3339 format. | getUpdatedAt(): ?string | setUpdatedAt(?string updatedAt): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\LoyaltyAccountBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyAccountExpiringPointDeadlineBuilder;

$loyaltyAccount = LoyaltyAccountBuilder::init(
    'program_id8'
)
    ->balance(198)
    ->createdAt('created_at0')
    ->customerId('customer_id0')
    ->enrolledAt('enrolled_at2')
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
    )->build();
```

