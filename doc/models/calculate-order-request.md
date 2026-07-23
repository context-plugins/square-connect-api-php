
# Calculate Order Request

## Structure

`CalculateOrderRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `order` | [`Order`](../../doc/models/order.md) | Required | Contains all information related to a single order to process with Square,<br>including line items that specify the products to purchase. `Order` objects also<br>include information about any associated tenders, refunds, and returns.<br><br>All Connect V2 Transactions have all been converted to Orders including all associated<br>itemization data. | getOrder(): Order | setOrder(Order order): void |
| `proposedRewards` | [`?(OrderReward[])`](../../doc/models/order-reward.md) | Optional | Identifies one or more loyalty reward tiers to apply during the order calculation.<br>The discounts defined by the reward tiers are added to the order only to preview the<br>effect of applying the specified rewards. The rewards do not correspond to actual<br>redemptions; that is, no `reward`s are created. Therefore, the reward `id`s are<br>random strings used only to reference the reward tier. | getProposedRewards(): ?array | setProposedRewards(?array proposedRewards): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CalculateOrderRequestBuilder;
use SquareConnectAPILib\Models\Builders\OrderBuilder;
use SquareConnectAPILib\Models\Builders\OrderLineItemDiscountBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;
use SquareConnectAPILib\Models\Builders\OrderFulfillmentBuilder;
use SquareConnectAPILib\Models\Builders\OrderFulfillmentPickupDetailsBuilder;
use SquareConnectAPILib\Models\Builders\OrderFulfillmentPickupDetailsCurbsidePickupDetailsBuilder;
use SquareConnectAPILib\Models\Builders\OrderFulfillmentShipmentDetailsBuilder;
use SquareConnectAPILib\Models\Builders\OrderRewardBuilder;

$calculateOrderRequest = CalculateOrderRequestBuilder::init(
    OrderBuilder::init(
        'location_id0'
    )
        ->closedAt('closed_at8')
        ->createdAt('created_at4')
        ->customerId('customer_id4')
        ->discounts(
            [
                OrderLineItemDiscountBuilder::init()
                    ->amountMoney(
                        MoneyBuilder::init()
                            ->amount(186)
                            ->currency('currency8')
                            ->build()
                    )
                    ->appliedMoney(
                        MoneyBuilder::init()
                            ->amount(196)
                            ->currency('currency8')
                            ->build()
                    )
                    ->catalogObjectId('catalog_object_id8')
                    ->catalogVersion(84)
                    ->metadata(
                        [
                            'key0' => 'metadata1'
                        ]
                    )
                    ->build(),
                OrderLineItemDiscountBuilder::init()
                    ->amountMoney(
                        MoneyBuilder::init()
                            ->amount(186)
                            ->currency('currency8')
                            ->build()
                    )
                    ->appliedMoney(
                        MoneyBuilder::init()
                            ->amount(196)
                            ->currency('currency8')
                            ->build()
                    )
                    ->catalogObjectId('catalog_object_id8')
                    ->catalogVersion(84)
                    ->metadata(
                        [
                            'key0' => 'metadata1'
                        ]
                    )
                    ->build()
            ]
        )
        ->fulfillments(
            [
                OrderFulfillmentBuilder::init()
                    ->metadata(
                        [
                            'key0' => 'metadata9'
                        ]
                    )
                    ->pickupDetails(
                        OrderFulfillmentPickupDetailsBuilder::init()
                            ->acceptedAt('accepted_at2')
                            ->autoCompleteDuration('auto_complete_duration2')
                            ->cancelReason('cancel_reason4')
                            ->canceledAt('canceled_at4')
                            ->curbsidePickupDetails(
                                OrderFulfillmentPickupDetailsCurbsidePickupDetailsBuilder::init()
                                    ->buyerArrivedAt('buyer_arrived_at8')
                                    ->curbsideDetails('curbside_details2')
                                    ->build()
                            )
                            ->build()
                    )
                    ->shipmentDetails(
                        OrderFulfillmentShipmentDetailsBuilder::init()
                            ->cancelReason('cancel_reason6')
                            ->canceledAt('canceled_at4')
                            ->carrier('carrier0')
                            ->expectedShippedAt('expected_shipped_at2')
                            ->failedAt('failed_at2')
                            ->build()
                    )
                    ->state('state0')
                    ->type('type6')
                    ->build(),
                OrderFulfillmentBuilder::init()
                    ->metadata(
                        [
                            'key0' => 'metadata9'
                        ]
                    )
                    ->pickupDetails(
                        OrderFulfillmentPickupDetailsBuilder::init()
                            ->acceptedAt('accepted_at2')
                            ->autoCompleteDuration('auto_complete_duration2')
                            ->cancelReason('cancel_reason4')
                            ->canceledAt('canceled_at4')
                            ->curbsidePickupDetails(
                                OrderFulfillmentPickupDetailsCurbsidePickupDetailsBuilder::init()
                                    ->buyerArrivedAt('buyer_arrived_at8')
                                    ->curbsideDetails('curbside_details2')
                                    ->build()
                            )
                            ->build()
                    )
                    ->shipmentDetails(
                        OrderFulfillmentShipmentDetailsBuilder::init()
                            ->cancelReason('cancel_reason6')
                            ->canceledAt('canceled_at4')
                            ->carrier('carrier0')
                            ->expectedShippedAt('expected_shipped_at2')
                            ->failedAt('failed_at2')
                            ->build()
                    )
                    ->state('state0')
                    ->type('type6')
                    ->build()
            ]
        )
        ->build()
)
    ->proposedRewards(
        [
            OrderRewardBuilder::init(
                'id0',
                'reward_tier_id6'
            )->build(),
            OrderRewardBuilder::init(
                'id0',
                'reward_tier_id6'
            )->build(),
            OrderRewardBuilder::init(
                'id0',
                'reward_tier_id6'
            )->build()
        ]
    )->build();
```

