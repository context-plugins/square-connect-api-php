
# Loyalty Account Expiring Point Deadline

Represents a set of points for a loyalty account that are scheduled to expire on a specific date.

## Structure

`LoyaltyAccountExpiringPointDeadline`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `expiresAt` | `string` | Required | The timestamp of when the points are scheduled to expire, in RFC 3339 format.<br><br>**Constraints**: *Minimum Length*: `1` | getExpiresAt(): string | setExpiresAt(string expiresAt): void |
| `points` | `int` | Required | The number of points scheduled to expire at the `expires_at` timestamp. | getPoints(): int | setPoints(int points): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\LoyaltyAccountExpiringPointDeadlineBuilder;

$loyaltyAccountExpiringPointDeadline = LoyaltyAccountExpiringPointDeadlineBuilder::init(
    'expires_at6',
    144
)->build();
```

