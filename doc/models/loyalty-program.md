
# Loyalty Program

Represents a Square loyalty program. Loyalty programs define how buyers can earn points and redeem points for rewards.
Square sellers can have only one loyalty program, which is created and managed from the Seller Dashboard.
For more information, see [Loyalty Program Overview](https://developer.squareup.com/docs/loyalty/overview).

## Structure

`LoyaltyProgram`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accrualRules` | [`LoyaltyProgramAccrualRule[]`](../../doc/models/loyalty-program-accrual-rule.md) | Required | Defines how buyers can earn loyalty points. | getAccrualRules(): array | setAccrualRules(array accrualRules): void |
| `createdAt` | `string` | Required | The timestamp when the program was created, in RFC 3339 format.<br><br>**Constraints**: *Minimum Length*: `1` | getCreatedAt(): string | setCreatedAt(string createdAt): void |
| `expirationPolicy` | [`?LoyaltyProgramExpirationPolicy`](../../doc/models/loyalty-program-expiration-policy.md) | Optional | Describes when the loyalty program expires. | getExpirationPolicy(): ?LoyaltyProgramExpirationPolicy | setExpirationPolicy(?LoyaltyProgramExpirationPolicy expirationPolicy): void |
| `id` | `string` | Required | The Square-assigned ID of the loyalty program. Updates to<br>the loyalty program do not modify the identifier.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `36` | getId(): string | setId(string id): void |
| `locationIds` | `string[]` | Required | The [locations](https://developer.squareup.com/reference/square_2021-08-18/objects/Location) at which the program is active.<br><br>**Constraints**: *Minimum Length*: `1` | getLocationIds(): array | setLocationIds(array locationIds): void |
| `rewardTiers` | [`LoyaltyProgramRewardTier[]`](../../doc/models/loyalty-program-reward-tier.md) | Required | The list of rewards for buyers, sorted by ascending points. | getRewardTiers(): array | setRewardTiers(array rewardTiers): void |
| `status` | `string` | Required | Whether the program is currently active. | getStatus(): string | setStatus(string status): void |
| `terminology` | [`LoyaltyProgramTerminology`](../../doc/models/loyalty-program-terminology.md) | Required | Represents the naming used for loyalty points. | getTerminology(): LoyaltyProgramTerminology | setTerminology(LoyaltyProgramTerminology terminology): void |
| `updatedAt` | `string` | Required | The timestamp when the reward was last updated, in RFC 3339 format.<br><br>**Constraints**: *Minimum Length*: `1` | getUpdatedAt(): string | setUpdatedAt(string updatedAt): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\LoyaltyProgramBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyProgramAccrualRuleBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyProgramRewardTierBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyProgramRewardDefinitionBuilder;
use SquareConnectAPILib\Models\Builders\CatalogObjectReferenceBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyProgramTerminologyBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyProgramExpirationPolicyBuilder;

$loyaltyProgram = LoyaltyProgramBuilder::init(
    [
        LoyaltyProgramAccrualRuleBuilder::init(
            'accrual_type6'
        )
            ->catalogObjectId('catalog_object_id0')
            ->excludedCategoryIds(
                [
                    'excluded_category_ids2'
                ]
            )
            ->excludedItemVariationIds(
                [
                    'excluded_item_variation_ids5',
                    'excluded_item_variation_ids4'
                ]
            )
            ->points(220)
            ->spendAmountMoney(
                MoneyBuilder::init()
                    ->amount(218)
                    ->currency('currency2')
                    ->build()
            )
            ->build()
    ],
    'created_at6',
    'id6',
    [
        'location_ids6',
        'location_ids7',
        'location_ids8'
    ],
    [
        LoyaltyProgramRewardTierBuilder::init(
            'created_at6',
            LoyaltyProgramRewardDefinitionBuilder::init(
                'discount_type8',
                'scope8'
            )
                ->catalogObjectIds(
                    [
                        'catalog_object_ids6'
                    ]
                )
                ->fixedDiscountMoney(
                    MoneyBuilder::init()
                        ->amount(36)
                        ->currency('currency4')
                        ->build()
                )
                ->maxDiscountMoney(
                    MoneyBuilder::init()
                        ->amount(84)
                        ->currency('currency0')
                        ->build()
                )
                ->percentageDiscount('percentage_discount2')
                ->build(),
            'id8',
            'name8',
            250
        )
            ->pricingRuleReference(
                CatalogObjectReferenceBuilder::init()
                    ->catalogVersion(218)
                    ->objectId('object_id0')
                    ->build()
            )
            ->build()
    ],
    'status2',
    LoyaltyProgramTerminologyBuilder::init(
        'one0',
        'other6'
    )->build(),
    'updated_at8'
)
    ->expirationPolicy(
        LoyaltyProgramExpirationPolicyBuilder::init(
            'expiration_duration0'
        )->build()
    )->build();
```

