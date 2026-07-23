
# Update Order Request

Defines the fields that are included in requests to the
[UpdateOrder](https://developer.squareup.com/reference/square_2021-08-18/orders-api/update-order) endpoint.

## Structure

`UpdateOrderRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `fieldsToClear` | `?(string[])` | Optional | The [dot notation paths](https://developer.squareup.com/docs/orders-api/manage-orders#on-dot-notation)<br>fields to clear. For example, `line_items[uid].note`.<br>For more information, see [Deleting fields](https://developer.squareup.com/docs/orders-api/manage-orders#delete-fields). | getFieldsToClear(): ?array | setFieldsToClear(?array fieldsToClear): void |
| `idempotencyKey` | `?string` | Optional | A value you specify that uniquely identifies this update request.<br><br>If you are unsure whether a particular update was applied to an order successfully,<br>you can reattempt it with the same idempotency key without<br>worrying about creating duplicate updates to the order.<br>The latest order version is returned.<br><br>For more information, see [Idempotency](https://developer.squareup.com/docs/basics/api101/idempotency).<br><br>**Constraints**: *Maximum Length*: `192` | getIdempotencyKey(): ?string | setIdempotencyKey(?string idempotencyKey): void |
| `order` | [`?Order`](../../doc/models/order.md) | Optional | Contains all information related to a single order to process with Square,<br>including line items that specify the products to purchase. `Order` objects also<br>include information about any associated tenders, refunds, and returns.<br><br>All Connect V2 Transactions have all been converted to Orders including all associated<br>itemization data. | getOrder(): ?Order | setOrder(?Order order): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\UpdateOrderRequestBuilder;
use SquareConnectAPILib\Models\Builders\OrderBuilder;
use SquareConnectAPILib\Models\Builders\OrderLineItemDiscountBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;
use SquareConnectAPILib\Models\Builders\OrderFulfillmentBuilder;
use SquareConnectAPILib\Models\Builders\OrderFulfillmentPickupDetailsBuilder;
use SquareConnectAPILib\Models\Builders\OrderFulfillmentPickupDetailsCurbsidePickupDetailsBuilder;
use SquareConnectAPILib\Models\Builders\OrderFulfillmentShipmentDetailsBuilder;

$updateOrderRequest = UpdateOrderRequestBuilder::init()
    ->fieldsToClear(
        [
            'fields_to_clear3',
            'fields_to_clear4',
            'fields_to_clear5'
        ]
    )
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

