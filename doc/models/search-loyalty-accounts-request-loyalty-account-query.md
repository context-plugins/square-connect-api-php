
# Search Loyalty Accounts Request Loyalty Account Query

The search criteria for the loyalty accounts.

## Structure

`SearchLoyaltyAccountsRequestLoyaltyAccountQuery`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `customerIds` | `?(string[])` | Optional | The set of customer IDs to use in the loyalty account search.<br><br>This cannot be combined with `mappings`.<br><br>Max: 30 customer IDs | getCustomerIds(): ?array | setCustomerIds(?array customerIds): void |
| `mappings` | [`?(LoyaltyAccountMapping[])`](../../doc/models/loyalty-account-mapping.md) | Optional | The set of mappings to use in the loyalty account search.<br><br>This cannot be combined with `customer_ids`.<br><br>Max: 30 mappings | getMappings(): ?array | setMappings(?array mappings): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\SearchLoyaltyAccountsRequestLoyaltyAccountQueryBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyAccountMappingBuilder;

$searchLoyaltyAccountsRequestLoyaltyAccountQuery = SearchLoyaltyAccountsRequestLoyaltyAccountQueryBuilder::init()
    ->customerIds(
        [
            'customer_ids5'
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
    ->build();
```

