
# Search Loyalty Rewards Request

A request to search for loyalty rewards.

## Structure

`SearchLoyaltyRewardsRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cursor` | `?string` | Optional | A pagination cursor returned by a previous call to<br>this endpoint. Provide this to retrieve the next set of<br>results for the original query.<br>For more information,<br>see [Pagination](https://developer.squareup.com/docs/basics/api101/pagination). | getCursor(): ?string | setCursor(?string cursor): void |
| `limit` | `?int` | Optional | The maximum number of results to return in the response.<br><br>**Constraints**: `>= 1`, `<= 30` | getLimit(): ?int | setLimit(?int limit): void |
| `query` | [`?SearchLoyaltyRewardsRequestLoyaltyRewardQuery`](../../doc/models/search-loyalty-rewards-request-loyalty-reward-query.md) | Optional | The set of search requirements. | getQuery(): ?SearchLoyaltyRewardsRequestLoyaltyRewardQuery | setQuery(?SearchLoyaltyRewardsRequestLoyaltyRewardQuery query): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\SearchLoyaltyRewardsRequestBuilder;
use SquareConnectAPILib\Models\Builders\SearchLoyaltyRewardsRequestLoyaltyRewardQueryBuilder;

$searchLoyaltyRewardsRequest = SearchLoyaltyRewardsRequestBuilder::init()
    ->cursor('cursor4')
    ->limit(30)
    ->query(
        SearchLoyaltyRewardsRequestLoyaltyRewardQueryBuilder::init(
            'loyalty_account_id0'
        )
            ->status('status8')
            ->build()
    )
    ->build();
```

