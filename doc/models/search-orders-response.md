
# Search Orders Response

Either the `order_entries` or `orders` field is set, depending on whether
`return_entries` is set on the [SearchOrdersRequest](https://developer.squareup.com/reference/square_2021-08-18/orders-api/search-orders).

## Structure

`SearchOrdersResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cursor` | `?string` | Optional | The pagination cursor to be used in a subsequent request. If unset,<br>this is the final response.<br>For more information, see [Pagination](https://developer.squareup.com/docs/basics/api101/pagination). | getCursor(): ?string | setCursor(?string cursor): void |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | [Errors](https://developer.squareup.com/reference/square_2021-08-18/objects/Error) encountered during the search. | getErrors(): ?array | setErrors(?array errors): void |
| `orderEntries` | [`?(OrderEntry[])`](../../doc/models/order-entry.md) | Optional | A list of [OrderEntries](https://developer.squareup.com/reference/square_2021-08-18/objects/OrderEntry) that fit the query<br>conditions. The list is populated only if `return_entries` is set to `true` in the request. | getOrderEntries(): ?array | setOrderEntries(?array orderEntries): void |
| `orders` | [`?(Order[])`](../../doc/models/order.md) | Optional | A list of<br>[Order](https://developer.squareup.com/reference/square_2021-08-18/objects/Order) objects that match the query conditions. The list is populated only if<br>`return_entries` is set to `false` in the request. | getOrders(): ?array | setOrders(?array orders): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\SearchOrdersResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\OrderEntryBuilder;
use SquareConnectAPILib\Models\Builders\OrderBuilder;
use SquareConnectAPILib\Models\Builders\OrderLineItemDiscountBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;
use SquareConnectAPILib\Models\Builders\OrderFulfillmentBuilder;
use SquareConnectAPILib\Models\Builders\OrderFulfillmentPickupDetailsBuilder;
use SquareConnectAPILib\Models\Builders\OrderFulfillmentPickupDetailsCurbsidePickupDetailsBuilder;
use SquareConnectAPILib\Models\Builders\OrderFulfillmentShipmentDetailsBuilder;

$searchOrdersResponse = SearchOrdersResponseBuilder::init()
    ->cursor('123')
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
    ->orderEntries(
        [
            OrderEntryBuilder::init()
                ->locationId('057P5VYJ4A5X1')
                ->orderId('CAISEM82RcpmcFBM0TfOyiHV3es')
                ->version(1)
                ->build(),
            OrderEntryBuilder::init()
                ->locationId('18YC4JDH91E1H')
                ->orderId('CAISENgvlJ6jLWAzERDzjyHVybY')
                ->version(182)
                ->build(),
            OrderEntryBuilder::init()
                ->locationId('057P5VYJ4A5X1')
                ->orderId('CAISEM52YcpmcWAzERDOyiWS3ty')
                ->version(182)
                ->build()
        ]
    )
    ->orders(
        [
            OrderBuilder::init(
                'location_id6'
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
                ->build(),
            OrderBuilder::init(
                'location_id6'
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
                ->build(),
            OrderBuilder::init(
                'location_id6'
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
                ->build()
        ]
    )
    ->build();
```

