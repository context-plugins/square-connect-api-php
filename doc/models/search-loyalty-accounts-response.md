
# Search Loyalty Accounts Response

A response that includes loyalty accounts that satisfy the search criteria.

## Structure

`SearchLoyaltyAccountsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cursor` | `?string` | Optional | The pagination cursor to use in a subsequent<br>request. If empty, this is the final response.<br>For more information,<br>see [Pagination](https://developer.squareup.com/docs/basics/api101/pagination). | getCursor(): ?string | setCursor(?string cursor): void |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `loyaltyAccounts` | [`?(LoyaltyAccount[])`](../../doc/models/loyalty-account.md) | Optional | The loyalty accounts that met the search criteria,  <br>in order of creation date. | getLoyaltyAccounts(): ?array | setLoyaltyAccounts(?array loyaltyAccounts): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\SearchLoyaltyAccountsResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyAccountBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyAccountExpiringPointDeadlineBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyAccountMappingBuilder;

$searchLoyaltyAccountsResponse = SearchLoyaltyAccountsResponseBuilder::init()
    ->cursor('cursor8')
    ->errors(
        [
            ErrorBuilder::init(
                'category8',
                'code8'
            )
                ->detail('detail6')
                ->field('field4')
                ->build(),
            ErrorBuilder::init(
                'category8',
                'code8'
            )
                ->detail('detail6')
                ->field('field4')
                ->build(),
            ErrorBuilder::init(
                'category8',
                'code8'
            )
                ->detail('detail6')
                ->field('field4')
                ->build()
        ]
    )
    ->loyaltyAccounts(
        [
            LoyaltyAccountBuilder::init(
                'd619f755-2d17-41f3-990d-c04ecedd64dd'
            )
                ->balance(10)
                ->createdAt('2020-05-08T21:44:32Z')
                ->customerId('Q8002FAM9V1EZ0ADB2T5609X6NET1H0')
                ->enrolledAt('enrolled_at4')
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
                )
                ->id('79b807d2-d786-46a9-933b-918028d7a8c5')
                ->lifetimePoints(20)
                ->mapping(
                    LoyaltyAccountMappingBuilder::init()
                        ->createdAt('2020-05-08T21:44:32Z')
                        ->id('66aaab3f-da99-49ed-8b19-b87f851c844f')
                        ->phoneNumber('+14155551234')
                        ->build()
                )
                ->updatedAt('2020-05-08T21:44:32Z')
                ->build()
        ]
    )
    ->build();
```

