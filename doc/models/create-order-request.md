
# Create Order Request

## Structure

`CreateOrderRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `idempotencyKey` | `?string` | Optional | A value you specify that uniquely identifies this<br>order among orders you have created.<br><br>If you are unsure whether a particular order was created successfully,<br>you can try it again with the same idempotency key without<br>worrying about creating duplicate orders.<br><br>For more information, see [Idempotency](https://developer.squareup.com/docs/basics/api101/idempotency).<br><br>**Constraints**: *Maximum Length*: `192` | getIdempotencyKey(): ?string | setIdempotencyKey(?string idempotencyKey): void |
| `order` | [`?Order`](../../doc/models/order.md) | Optional | Contains all information related to a single order to process with Square,<br>including line items that specify the products to purchase. `Order` objects also<br>include information about any associated tenders, refunds, and returns.<br><br>All Connect V2 Transactions have all been converted to Orders including all associated<br>itemization data. | getOrder(): ?Order | setOrder(?Order order): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CreateOrderRequestBuilder;
use SquareConnectAPILib\Models\Builders\OrderBuilder;
use SquareConnectAPILib\Models\Builders\OrderLineItemDiscountBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;
use SquareConnectAPILib\Models\Builders\OrderFulfillmentBuilder;
use SquareConnectAPILib\Models\Builders\OrderFulfillmentPickupDetailsBuilder;
use SquareConnectAPILib\Models\Builders\OrderFulfillmentPickupDetailsCurbsidePickupDetailsBuilder;
use SquareConnectAPILib\Models\Builders\OrderFulfillmentShipmentDetailsBuilder;

$createOrderRequest = CreateOrderRequestBuilder::init()
    ->idempotencyKey('idempotency_key8')
    ->order(
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
    ->build();
```

