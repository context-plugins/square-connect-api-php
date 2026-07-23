
# Calculate Order Response

## Structure

`CalculateOrderResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `order` | [`?Order`](../../doc/models/order.md) | Optional | Contains all information related to a single order to process with Square,<br>including line items that specify the products to purchase. `Order` objects also<br>include information about any associated tenders, refunds, and returns.<br><br>All Connect V2 Transactions have all been converted to Orders including all associated<br>itemization data. | getOrder(): ?Order | setOrder(?Order order): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CalculateOrderResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\OrderBuilder;
use SquareConnectAPILib\Models\Builders\OrderLineItemDiscountBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;
use SquareConnectAPILib\Models\Builders\OrderFulfillmentBuilder;
use SquareConnectAPILib\Models\Builders\OrderFulfillmentPickupDetailsBuilder;
use SquareConnectAPILib\Models\Builders\OrderFulfillmentPickupDetailsCurbsidePickupDetailsBuilder;
use SquareConnectAPILib\Models\Builders\OrderFulfillmentShipmentDetailsBuilder;
use SquareConnectAPILib\Models\Builders\OrderLineItemBuilder;
use SquareConnectAPILib\Models\Builders\OrderLineItemAppliedDiscountBuilder;
use SquareConnectAPILib\Models\Builders\OrderMoneyAmountsBuilder;

$calculateOrderResponse = CalculateOrderResponseBuilder::init()
    ->errors(
        [
            ErrorBuilder::init(
                'category8',
                'code8'
            )
                ->detail('detail6')
                ->field('field4')
                ->build()
        ]
    )
    ->order(
        OrderBuilder::init(
            'D7AVYMEAPJ3A3'
        )
            ->closedAt('closed_at8')
            ->createdAt('2020-05-18T16:30:49.614Z')
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
                                ->amount(550)
                                ->currency('USD')
                                ->build()
                        )
                        ->catalogObjectId('catalog_object_id8')
                        ->catalogVersion(84)
                        ->metadata(
                            [
                                'key0' => 'metadata1'
                            ]
                        )
                        ->name('50% Off')
                        ->percentage('50')
                        ->scope('ORDER')
                        ->type('FIXED_PERCENTAGE')
                        ->uid('zGsRZP69aqSSR9lq9euSPB')
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
            ->lineItems(
                [
                    OrderLineItemBuilder::init(
                        '1'
                    )
                        ->appliedDiscounts(
                            [
                                OrderLineItemAppliedDiscountBuilder::init(
                                    'zGsRZP69aqSSR9lq9euSPB'
                                )
                                    ->appliedMoney(
                                        MoneyBuilder::init()
                                            ->amount(250)
                                            ->currency('USD')
                                            ->build()
                                    )
                                    ->uid('9zr9S4dxvPAixvn0lpa1VC')
                                    ->build()
                            ]
                        )
                        ->basePriceMoney(
                            MoneyBuilder::init()
                                ->amount(500)
                                ->currency('USD')
                                ->build()
                        )
                        ->grossSalesMoney(
                            MoneyBuilder::init()
                                ->amount(500)
                                ->currency('USD')
                                ->build()
                        )
                        ->name('Item 1')
                        ->totalDiscountMoney(
                            MoneyBuilder::init()
                                ->amount(250)
                                ->currency('USD')
                                ->build()
                        )
                        ->totalMoney(
                            MoneyBuilder::init()
                                ->amount(250)
                                ->currency('USD')
                                ->build()
                        )
                        ->totalTaxMoney(
                            MoneyBuilder::init()
                                ->amount(0)
                                ->currency('USD')
                                ->build()
                        )
                        ->uid('ULkg0tQTRK2bkU9fNv3IJD')
                        ->variationTotalPriceMoney(
                            MoneyBuilder::init()
                                ->amount(500)
                                ->currency('USD')
                                ->build()
                        )
                        ->build(),
                    OrderLineItemBuilder::init(
                        '2'
                    )
                        ->appliedDiscounts(
                            [
                                OrderLineItemAppliedDiscountBuilder::init(
                                    'zGsRZP69aqSSR9lq9euSPB'
                                )
                                    ->appliedMoney(
                                        MoneyBuilder::init()
                                            ->amount(300)
                                            ->currency('USD')
                                            ->build()
                                    )
                                    ->uid('qa8LwwZK82FgSEkQc2HYVC')
                                    ->build()
                            ]
                        )
                        ->basePriceMoney(
                            MoneyBuilder::init()
                                ->amount(300)
                                ->currency('USD')
                                ->build()
                        )
                        ->grossSalesMoney(
                            MoneyBuilder::init()
                                ->amount(600)
                                ->currency('USD')
                                ->build()
                        )
                        ->name('Item 2')
                        ->totalDiscountMoney(
                            MoneyBuilder::init()
                                ->amount(300)
                                ->currency('USD')
                                ->build()
                        )
                        ->totalMoney(
                            MoneyBuilder::init()
                                ->amount(300)
                                ->currency('USD')
                                ->build()
                        )
                        ->totalTaxMoney(
                            MoneyBuilder::init()
                                ->amount(0)
                                ->currency('USD')
                                ->build()
                        )
                        ->uid('mumY8Nun4BC5aKe2yyx5a')
                        ->variationTotalPriceMoney(
                            MoneyBuilder::init()
                                ->amount(600)
                                ->currency('USD')
                                ->build()
                        )
                        ->build()
                ]
            )
            ->netAmounts(
                OrderMoneyAmountsBuilder::init()
                    ->discountMoney(
                        MoneyBuilder::init()
                            ->amount(550)
                            ->currency('USD')
                            ->build()
                    )
                    ->serviceChargeMoney(
                        MoneyBuilder::init()
                            ->amount(0)
                            ->currency('USD')
                            ->build()
                    )
                    ->taxMoney(
                        MoneyBuilder::init()
                            ->amount(0)
                            ->currency('USD')
                            ->build()
                    )
                    ->tipMoney(
                        MoneyBuilder::init()
                            ->amount(0)
                            ->currency('USD')
                            ->build()
                    )
                    ->totalMoney(
                        MoneyBuilder::init()
                            ->amount(550)
                            ->currency('USD')
                            ->build()
                    )
                    ->build()
            )
            ->state('OPEN')
            ->totalDiscountMoney(
                MoneyBuilder::init()
                    ->amount(550)
                    ->currency('USD')
                    ->build()
            )
            ->totalMoney(
                MoneyBuilder::init()
                    ->amount(550)
                    ->currency('USD')
                    ->build()
            )
            ->totalServiceChargeMoney(
                MoneyBuilder::init()
                    ->amount(0)
                    ->currency('USD')
                    ->build()
            )
            ->totalTaxMoney(
                MoneyBuilder::init()
                    ->amount(0)
                    ->currency('USD')
                    ->build()
            )
            ->totalTipMoney(
                MoneyBuilder::init()
                    ->amount(0)
                    ->currency('USD')
                    ->build()
            )
            ->updatedAt('2020-05-18T16:30:49.614Z')
            ->version(1)
            ->build()
    )
    ->build();
```

