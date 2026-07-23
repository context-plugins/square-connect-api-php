
# Batch Retrieve Orders Response

Defines the fields that are included in the response body of
a request to the `BatchRetrieveOrders` endpoint.

## Structure

`BatchRetrieveOrdersResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `orders` | [`?(Order[])`](../../doc/models/order.md) | Optional | The requested orders. This will omit any requested orders that do not exist. | getOrders(): ?array | setOrders(?array orders): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\BatchRetrieveOrdersResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\OrderBuilder;
use SquareConnectAPILib\Models\Builders\OrderLineItemDiscountBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;
use SquareConnectAPILib\Models\Builders\OrderFulfillmentBuilder;
use SquareConnectAPILib\Models\Builders\OrderFulfillmentPickupDetailsBuilder;
use SquareConnectAPILib\Models\Builders\OrderFulfillmentPickupDetailsCurbsidePickupDetailsBuilder;
use SquareConnectAPILib\Models\Builders\OrderFulfillmentShipmentDetailsBuilder;
use SquareConnectAPILib\Models\Builders\OrderLineItemBuilder;

$batchRetrieveOrdersResponse = BatchRetrieveOrdersResponseBuilder::init()
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
    ->orders(
        [
            OrderBuilder::init(
                '057P5VYJ4A5X1'
            )
                ->closedAt('closed_at4')
                ->createdAt('created_at0')
                ->customerId('customer_id0')
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
                            ->build()
                    ]
                )
                ->id('CAISEM82RcpmcFBM0TfOyiHV3es')
                ->lineItems(
                    [
                        OrderLineItemBuilder::init(
                            '1'
                        )
                            ->basePriceMoney(
                                MoneyBuilder::init()
                                    ->amount(1599)
                                    ->currency('USD')
                                    ->build()
                            )
                            ->name('Awesome product')
                            ->totalMoney(
                                MoneyBuilder::init()
                                    ->amount(1599)
                                    ->currency('USD')
                                    ->build()
                            )
                            ->uid('945986d1-9586-11e6-ad5a-28cfe92138cf')
                            ->build(),
                        OrderLineItemBuilder::init(
                            '3'
                        )
                            ->basePriceMoney(
                                MoneyBuilder::init()
                                    ->amount(2000)
                                    ->currency('USD')
                                    ->build()
                            )
                            ->name('Another awesome product')
                            ->totalMoney(
                                MoneyBuilder::init()
                                    ->amount(6000)
                                    ->currency('USD')
                                    ->build()
                            )
                            ->uid('a8f4168c-9586-11e6-bdf0-28cfe92138cf')
                            ->build()
                    ]
                )
                ->referenceId('my-order-001')
                ->totalMoney(
                    MoneyBuilder::init()
                        ->amount(7599)
                        ->currency('USD')
                        ->build()
                )
                ->build()
        ]
    )
    ->build();
```

