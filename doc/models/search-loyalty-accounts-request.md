
# Search Loyalty Accounts Request

A request to search for loyalty accounts.

## Structure

`SearchLoyaltyAccountsRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cursor` | `?string` | Optional | A pagination cursor returned by a previous call to<br>this endpoint. Provide this to retrieve the next set of<br>results for the original query.<br><br>For more information,<br>see [Pagination](https://developer.squareup.com/docs/basics/api101/pagination). | getCursor(): ?string | setCursor(?string cursor): void |
| `limit` | `?int` | Optional | The maximum number of results to include in the response.<br><br>**Constraints**: `>= 1`, `<= 30` | getLimit(): ?int | setLimit(?int limit): void |
| `query` | [`?SearchLoyaltyAccountsRequestLoyaltyAccountQuery`](../../doc/models/search-loyalty-accounts-request-loyalty-account-query.md) | Optional | The search criteria for the loyalty accounts. | getQuery(): ?SearchLoyaltyAccountsRequestLoyaltyAccountQuery | setQuery(?SearchLoyaltyAccountsRequestLoyaltyAccountQuery query): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\SearchLoyaltyAccountsRequestBuilder;
use SquareConnectAPILib\Models\Builders\SearchLoyaltyAccountsRequestLoyaltyAccountQueryBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyAccountMappingBuilder;

$searchLoyaltyAccountsRequest = SearchLoyaltyAccountsRequestBuilder::init()
    ->cursor('cursor4')
    ->limit(30)
    ->query(
        SearchLoyaltyAccountsRequestLoyaltyAccountQueryBuilder::init()
            ->customerIds(
                [
                    'customer_ids1',
                    'customer_ids2',
                    'customer_ids3'
                ]
            )
            ->mappings(
                [
                    LoyaltyAccountMappingBuilder::init()
                        ->createdAt('created_at6')
                        ->id('id8')
                        ->phoneNumber('phone_number4')
                        ->build(),
                    LoyaltyAccountMappingBuilder::init()
                        ->createdAt('created_at6')
                        ->id('id8')
                        ->phoneNumber('phone_number4')
                        ->build()
                ]
            )
            ->build()
    )
    ->build();
```

