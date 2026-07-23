
# Loyalty Event Loyalty Account Filter

Filter events by loyalty account.

## Structure

`LoyaltyEventLoyaltyAccountFilter`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `loyaltyAccountId` | `string` | Required | The ID of the [loyalty account](https://developer.squareup.com/reference/square_2021-08-18/objects/LoyaltyAccount) associated with loyalty events.<br><br>**Constraints**: *Minimum Length*: `1` | getLoyaltyAccountId(): string | setLoyaltyAccountId(string loyaltyAccountId): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\LoyaltyEventLoyaltyAccountFilterBuilder;

$loyaltyEventLoyaltyAccountFilter = LoyaltyEventLoyaltyAccountFilterBuilder::init(
    'loyalty_account_id6'
)->build();
```

