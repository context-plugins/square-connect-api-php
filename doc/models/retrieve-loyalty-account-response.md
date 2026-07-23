
# Retrieve Loyalty Account Response

A response that includes the loyalty account.

## Structure

`RetrieveLoyaltyAccountResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `loyaltyAccount` | [`?LoyaltyAccount`](../../doc/models/loyalty-account.md) | Optional | Describes a loyalty account. For more information, see<br>[Manage Loyalty Accounts Using the Loyalty API](https://developer.squareup.com/docs/loyalty-api/overview). | getLoyaltyAccount(): ?LoyaltyAccount | setLoyaltyAccount(?LoyaltyAccount loyaltyAccount): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\RetrieveLoyaltyAccountResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyAccountBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyAccountExpiringPointDeadlineBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyAccountMappingBuilder;

$retrieveLoyaltyAccountResponse = RetrieveLoyaltyAccountResponseBuilder::init()
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
                ->build()
        ]
    )
    ->loyaltyAccount(
        LoyaltyAccountBuilder::init(
            'd619f755-2d17-41f3-990d-c04ecedd64dd'
        )
            ->balance(10)
            ->createdAt('2020-05-08T21:44:32Z')
            ->customerId('Q8002FAM9V1EZ0ADB2T5609X6NET1H0')
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
    )
    ->build();
```

