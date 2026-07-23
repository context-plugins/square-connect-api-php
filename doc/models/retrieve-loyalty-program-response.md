
# Retrieve Loyalty Program Response

A response that contains the loyalty program.

## Structure

`RetrieveLoyaltyProgramResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `program` | [`?LoyaltyProgram`](../../doc/models/loyalty-program.md) | Optional | Represents a Square loyalty program. Loyalty programs define how buyers can earn points and redeem points for rewards.<br>Square sellers can have only one loyalty program, which is created and managed from the Seller Dashboard.<br>For more information, see [Loyalty Program Overview](https://developer.squareup.com/docs/loyalty/overview). | getProgram(): ?LoyaltyProgram | setProgram(?LoyaltyProgram program): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\RetrieveLoyaltyProgramResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyProgramBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyProgramAccrualRuleBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyProgramRewardTierBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyProgramRewardDefinitionBuilder;
use SquareConnectAPILib\Models\Builders\CatalogObjectReferenceBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyProgramTerminologyBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyProgramExpirationPolicyBuilder;

$retrieveLoyaltyProgramResponse = RetrieveLoyaltyProgramResponseBuilder::init()
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
    ->program(
        LoyaltyProgramBuilder::init(
            [
                LoyaltyProgramAccrualRuleBuilder::init(
                    'SPEND'
                )
                    ->catalogObjectId('catalog_object_id0')
                    ->excludedCategoryIds(
                        [
                            '7ZERJKO5PVYXCVUHV2JCZ2UG',
                            'FQKAOJE5C4FIMF5A2URMLW6V'
                        ]
                    )
                    ->excludedItemVariationIds(
                        [
                            'CBZXBUVVTYUBZGQO44RHMR6B',
                            'EDILT24Z2NISEXDKGY6HP7XV'
                        ]
                    )
                    ->points(1)
                    ->spendAmountMoney(
                        MoneyBuilder::init()
                            ->amount(100)
                            ->currency('currency2')
                            ->build()
                    )
                    ->build()
            ],
            '2020-04-20T16:55:11Z',
            'd619f755-2d17-41f3-990d-c04ecedd64dd',
            [
                'P034NEENMD09F'
            ],
            [
                LoyaltyProgramRewardTierBuilder::init(
                    '2020-04-20T16:55:11Z',
                    LoyaltyProgramRewardDefinitionBuilder::init(
                        'FIXED_PERCENTAGE',
                        'ORDER'
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
                        ->percentageDiscount('10')
                        ->build(),
                    'e1b39225-9da5-43d1-a5db-782cdd8ad94f',
                    '10% off entire sale',
                    10
                )
                    ->pricingRuleReference(
                        CatalogObjectReferenceBuilder::init()
                            ->catalogVersion(1605486402527)
                            ->objectId('74C4JSHESNLTB2A7ITO5HO6F')
                            ->build()
                    )
                    ->build()
            ],
            'ACTIVE',
            LoyaltyProgramTerminologyBuilder::init(
                'Point',
                'Points'
            )->build(),
            '2020-05-01T02:00:02Z'
        )
            ->expirationPolicy(
                LoyaltyProgramExpirationPolicyBuilder::init(
                    'expiration_duration0'
                )->build()
            )->build()
    )->build();
```

