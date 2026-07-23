
# Catalog Subscription Plan

Describes a subscription plan. For more information, see
[Set Up and Manage a Subscription Plan](https://developer.squareup.com/docs/subscriptions-api/setup-plan).

## Structure

`CatalogSubscriptionPlan`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `name` | `string` | Required | The name of the plan. | getName(): string | setName(string name): void |
| `phases` | [`SubscriptionPhase[]`](../../doc/models/subscription-phase.md) | Required | A list of SubscriptionPhase containing the [SubscriptionPhase](https://developer.squareup.com/reference/square_2021-08-18/objects/SubscriptionPhase) for this plan. | getPhases(): array | setPhases(array phases): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CatalogSubscriptionPlanBuilder;
use SquareConnectAPILib\Models\Builders\SubscriptionPhaseBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;

$catalogSubscriptionPlan = CatalogSubscriptionPlanBuilder::init(
    'name2',
    [
        SubscriptionPhaseBuilder::init(
            'cadence2',
            MoneyBuilder::init()
                ->amount(66)
                ->currency('currency2')
                ->build()
        )
            ->ordinal(78)
            ->periods(112)
            ->uid('uid0')
            ->build()
    ]
)->build();
```

