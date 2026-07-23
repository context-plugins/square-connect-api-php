
# Update Order Response

Defines the fields that are included in the response body of
a request to the [UpdateOrder](https://developer.squareup.com/reference/square_2021-08-18/orders-api/update-order) endpoint.

## Structure

`UpdateOrderResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `order` | [`?Order`](../../doc/models/order.md) | Optional | Contains all information related to a single order to process with Square,<br>including line items that specify the products to purchase. `Order` objects also<br>include information about any associated tenders, refunds, and returns.<br><br>All Connect V2 Transactions have all been converted to Orders including all associated<br>itemization data. | getOrder(): ?Order | setOrder(?Order order): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\UpdateOrderResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\OrderBuilder;
use SquareConnectAPILib\Models\Builders\OrderLineItemDiscountBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;
use SquareConnectAPILib\Models\Builders\OrderFulfillmentBuilder;
use SquareConnectAPILib\Models\Builders\OrderFulfillmentPickupDetailsBuilder;
use SquareConnectAPILib\Models\Builders\OrderFulfillmentPickupDetailsCurbsidePickupDetailsBuilder;
use SquareConnectAPILib\Models\Builders\OrderFulfillmentShipmentDetailsBuilder;
use SquareConnectAPILib\Models\Builders\OrderLineItemBuilder;
use SquareConnectAPILib\Models\Builders\OrderMoneyAmountsBuilder;
use SquareConnectAPILib\Models\Builders\OrderSourceBuilder;

$updateOrderResponse = UpdateOrderResponseBuilder::init()
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
    ->order(
        OrderBuilder::init(
            'MXVQSVNDGN3C8'
        )
            ->closedAt('closed_at8')
            ->createdAt('2019-08-23T18:26:18.243Z')
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
            ->id('DREk7wJcyXNHqULq8JJ2iPAsluJZY')
            ->lineItems(
                [
                    OrderLineItemBuilder::init(
                        '1'
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
                        ->name('Small Coffee')
                        ->totalDiscountMoney(
                            MoneyBuilder::init()
                                ->amount(0)
                                ->currency('USD')
                                ->build()
                        )
                        ->totalMoney(
                            MoneyBuilder::init()
                                ->amount(500)
                                ->currency('USD')
                                ->build()
                        )
                        ->totalTaxMoney(
                            MoneyBuilder::init()
                                ->amount(0)
                                ->currency('USD')
                                ->build()
                        )
                        ->uid('EuYkakhmu3ksHIds5Hiot')
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
                        ->basePriceMoney(
                            MoneyBuilder::init()
                                ->amount(200)
                                ->currency('USD')
                                ->build()
                        )
                        ->grossSalesMoney(
                            MoneyBuilder::init()
                                ->amount(400)
                                ->currency('USD')
                                ->build()
                        )
                        ->name('COOKIE')
                        ->totalDiscountMoney(
                            MoneyBuilder::init()
                                ->amount(0)
                                ->currency('USD')
                                ->build()
                        )
                        ->totalMoney(
                            MoneyBuilder::init()
                                ->amount(400)
                                ->currency('USD')
                                ->build()
                        )
                        ->totalTaxMoney(
                            MoneyBuilder::init()
                                ->amount(0)
                                ->currency('USD')
                                ->build()
                        )
                        ->uid('cookie_uid')
                        ->variationTotalPriceMoney(
                            MoneyBuilder::init()
                                ->amount(400)
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
                            ->amount(0)
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
                    ->totalMoney(
                        MoneyBuilder::init()
                            ->amount(900)
                            ->currency('USD')
                            ->build()
                    )
                    ->build()
            )
            ->source(
                OrderSourceBuilder::init()
                    ->name('Cookies')
                    ->build()
            )
            ->state('OPEN')
            ->totalDiscountMoney(
                MoneyBuilder::init()
                    ->amount(0)
                    ->currency('USD')
                    ->build()
            )
            ->totalMoney(
                MoneyBuilder::init()
                    ->amount(900)
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
            ->updatedAt('2019-08-23T18:33:47.523Z')
            ->version(2)
            ->build()
    )
    ->build();
```

