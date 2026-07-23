
# Loyalty Program Reward Tier

Represents a reward tier in a loyalty program. A reward tier defines how buyers can redeem points for a reward, such as the number of points required and the value and scope of the discount. A loyalty program can offer multiple reward tiers.

## Structure

`LoyaltyProgramRewardTier`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `createdAt` | `string` | Required | The timestamp when the reward tier was created, in RFC 3339 format. | getCreatedAt(): string | setCreatedAt(string createdAt): void |
| `definition` | [`LoyaltyProgramRewardDefinition`](../../doc/models/loyalty-program-reward-definition.md) | Required | Provides details about the reward tier discount. DEPRECATED at version 2020-12-16. Discount details<br>are now defined using a catalog pricing rule and other catalog objects. For more information, see<br>[Get discount details for the reward](https://developer.squareup.com/docs/loyalty-api/overview#get-discount-details). | getDefinition(): LoyaltyProgramRewardDefinition | setDefinition(LoyaltyProgramRewardDefinition definition): void |
| `id` | `string` | Required | The Square-assigned ID of the reward tier.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `36` | getId(): string | setId(string id): void |
| `name` | `string` | Required | The name of the reward tier.<br><br>**Constraints**: *Minimum Length*: `1` | getName(): string | setName(string name): void |
| `points` | `int` | Required | The points exchanged for the reward tier.<br><br>**Constraints**: `>= 1` | getPoints(): int | setPoints(int points): void |
| `pricingRuleReference` | [`?CatalogObjectReference`](../../doc/models/catalog-object-reference.md) | Optional | A reference to a Catalog object at a specific version. In general this is<br>used as an entry point into a graph of catalog objects, where the objects exist<br>at a specific version. | getPricingRuleReference(): ?CatalogObjectReference | setPricingRuleReference(?CatalogObjectReference pricingRuleReference): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\LoyaltyProgramRewardTierBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyProgramRewardDefinitionBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;
use SquareConnectAPILib\Models\Builders\CatalogObjectReferenceBuilder;

$loyaltyProgramRewardTier = LoyaltyProgramRewardTierBuilder::init(
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
    58
)
    ->pricingRuleReference(
        CatalogObjectReferenceBuilder::init()
            ->catalogVersion(218)
            ->objectId('object_id0')
            ->build()
    )
    ->build();
```

