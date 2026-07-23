
# Search Loyalty Rewards Request Loyalty Reward Query

The set of search requirements.

## Structure

`SearchLoyaltyRewardsRequestLoyaltyRewardQuery`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `loyaltyAccountId` | `string` | Required | The ID of the [loyalty account](https://developer.squareup.com/reference/square_2021-08-18/objects/LoyaltyAccount) to which the loyalty reward belongs. | getLoyaltyAccountId(): string | setLoyaltyAccountId(string loyaltyAccountId): void |
| `status` | `?string` | Optional | The status of the loyalty reward. | getStatus(): ?string | setStatus(?string status): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\SearchLoyaltyRewardsRequestLoyaltyRewardQueryBuilder;

$searchLoyaltyRewardsRequestLoyaltyRewardQuery = SearchLoyaltyRewardsRequestLoyaltyRewardQueryBuilder::init(
    'loyalty_account_id8'
)
    ->status('status0')
    ->build();
```

