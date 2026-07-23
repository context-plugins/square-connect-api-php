
# Pay Order Response

Defines the fields that are included in the response body of a request to the
[PayOrder](https://developer.squareup.com/reference/square_2021-08-18/orders-api/pay-order) endpoint.

## Structure

`PayOrderResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `order` | [`?Order`](../../doc/models/order.md) | Optional | Contains all information related to a single order to process with Square,<br>including line items that specify the products to purchase. `Order` objects also<br>include information about any associated tenders, refunds, and returns.<br><br>All Connect V2 Transactions have all been converted to Orders including all associated<br>itemization data. | getOrder(): ?Order | setOrder(?Order order): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\PayOrderResponseBuilder;
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
use SquareConnectAPILib\Models\Builders\TenderBuilder;
use SquareConnectAPILib\Models\Builders\TenderCardDetailsBuilder;
use SquareConnectAPILib\Models\Builders\CardBuilder;

$payOrderResponse = PayOrderResponseBuilder::init()
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
            'P3CCK6HSNDAS7'
        )
            ->closedAt('2019-08-06T02:47:37.140Z')
            ->createdAt('2019-08-06T02:47:35.693Z')
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
            ->id('lgwOlEityYPJtcuvKTVKT1pA986YY')
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
                        ->name('Item 1')
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
                        ->uid('QW6kofLHJK7JEKMjlSVP5C')
                        ->build(),
                    OrderLineItemBuilder::init(
                        '2'
                    )
                        ->basePriceMoney(
                            MoneyBuilder::init()
                                ->amount(750)
                                ->currency('USD')
                                ->build()
                        )
                        ->grossSalesMoney(
                            MoneyBuilder::init()
                                ->amount(1500)
                                ->currency('USD')
                                ->build()
                        )
                        ->name('Item 2')
                        ->totalDiscountMoney(
                            MoneyBuilder::init()
                                ->amount(0)
                                ->currency('USD')
                                ->build()
                        )
                        ->totalMoney(
                            MoneyBuilder::init()
                                ->amount(1500)
                                ->currency('USD')
                                ->build()
                        )
                        ->totalTaxMoney(
                            MoneyBuilder::init()
                                ->amount(0)
                                ->currency('USD')
                                ->build()
                        )
                        ->uid('zhw8MNfRGdFQMI2WE1UBJD')
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
                    ->tipMoney(
                        MoneyBuilder::init()
                            ->amount(0)
                            ->currency('USD')
                            ->build()
                    )
                    ->totalMoney(
                        MoneyBuilder::init()
                            ->amount(2000)
                            ->currency('USD')
                            ->build()
                    )
                    ->build()
            )
            ->source(
                OrderSourceBuilder::init()
                    ->name('Source Name')
                    ->build()
            )
            ->state('COMPLETED')
            ->tenders(
                [
                    TenderBuilder::init(
                        'CARD'
                    )
                        ->amountMoney(
                            MoneyBuilder::init()
                                ->amount(1000)
                                ->currency('USD')
                                ->build()
                        )
                        ->cardDetails(
                            TenderCardDetailsBuilder::init()
                                ->card(
                                    CardBuilder::init()
                                        ->cardBrand('VISA')
                                        ->expMonth(2)
                                        ->expYear(2022)
                                        ->fingerprint('sq-1-n_BL15KP87ClDa4-h2nXOI0fp5VnxNH6hfhzqhptTfAgxgLuGFcg6jIPngDz4IkkTQ')
                                        ->last4('1111')
                                        ->build()
                                )
                                ->entryMethod('KEYED')
                                ->status('CAPTURED')
                                ->build()
                        )
                        ->createdAt('2019-08-06T02:47:36.293Z')
                        ->id('EnZdNAlWCmfh6Mt5FMNST1o7taB')
                        ->locationId('P3CCK6HSNDAS7')
                        ->paymentId('EnZdNAlWCmfh6Mt5FMNST1o7taB')
                        ->transactionId('lgwOlEityYPJtcuvKTVKT1pA986YY')
                        ->build(),
                    TenderBuilder::init(
                        'CARD'
                    )
                        ->amountMoney(
                            MoneyBuilder::init()
                                ->amount(1000)
                                ->currency('USD')
                                ->build()
                        )
                        ->cardDetails(
                            TenderCardDetailsBuilder::init()
                                ->card(
                                    CardBuilder::init()
                                        ->cardBrand('VISA')
                                        ->expMonth(2)
                                        ->expYear(2022)
                                        ->fingerprint('sq-1-n_BL15KP87ClDa4-h2nXOI0fp5VnxNH6hfhzqhptTfAgxgLuGFcg6jIPngDz4IkkTQ')
                                        ->last4('1111')
                                        ->build()
                                )
                                ->entryMethod('KEYED')
                                ->status('CAPTURED')
                                ->build()
                        )
                        ->createdAt('2019-08-06T02:47:36.809Z')
                        ->id('0LRiVlbXVwe8ozu4KbZxd12mvaB')
                        ->locationId('P3CCK6HSNDAS7')
                        ->paymentId('0LRiVlbXVwe8ozu4KbZxd12mvaB')
                        ->transactionId('lgwOlEityYPJtcuvKTVKT1pA986YY')
                        ->build()
                ]
            )
            ->totalDiscountMoney(
                MoneyBuilder::init()
                    ->amount(0)
                    ->currency('USD')
                    ->build()
            )
            ->totalMoney(
                MoneyBuilder::init()
                    ->amount(2000)
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
            ->updatedAt('2019-08-06T02:47:37.140Z')
            ->version(4)
            ->build()
    )
    ->build();
```

