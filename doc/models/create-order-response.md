
# Create Order Response

Defines the fields that are included in the response body of
a request to the `CreateOrder` endpoint.

Either `errors` or `order` is present in a given response, but never both.

## Structure

`CreateOrderResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `order` | [`?Order`](../../doc/models/order.md) | Optional | Contains all information related to a single order to process with Square,<br>including line items that specify the products to purchase. `Order` objects also<br>include information about any associated tenders, refunds, and returns.<br><br>All Connect V2 Transactions have all been converted to Orders including all associated<br>itemization data. | getOrder(): ?Order | setOrder(?Order order): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CreateOrderResponseBuilder;
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
use SquareConnectAPILib\Models\Builders\OrderLineItemAppliedTaxBuilder;
use SquareConnectAPILib\Models\Builders\OrderLineItemModifierBuilder;
use SquareConnectAPILib\Models\Builders\OrderMoneyAmountsBuilder;
use SquareConnectAPILib\Models\Builders\OrderSourceBuilder;
use SquareConnectAPILib\Models\Builders\OrderLineItemTaxBuilder;

$createOrderResponse = CreateOrderResponseBuilder::init()
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
            '057P5VYJ4A5X1'
        )
            ->closedAt('closed_at8')
            ->createdAt('2020-01-17T20:47:53.293Z')
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
                                ->amount(30)
                                ->currency('USD')
                                ->build()
                        )
                        ->catalogObjectId('DB7L55ZH2BGWI4H23ULIWOQ7')
                        ->catalogVersion(84)
                        ->metadata(
                            [
                                'key0' => 'metadata1'
                            ]
                        )
                        ->name('Membership Discount')
                        ->percentage('0.5')
                        ->scope('ORDER')
                        ->type('FIXED_PERCENTAGE')
                        ->uid('membership-discount')
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
                                ->amount(303)
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
                        ->name('Labor Day Sale')
                        ->percentage('5')
                        ->scope('ORDER')
                        ->type('FIXED_PERCENTAGE')
                        ->uid('labor-day-sale')
                        ->build(),
                    OrderLineItemDiscountBuilder::init()
                        ->amountMoney(
                            MoneyBuilder::init()
                                ->amount(100)
                                ->currency('USD')
                                ->build()
                        )
                        ->appliedMoney(
                            MoneyBuilder::init()
                                ->amount(100)
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
                        ->name('Sale - $1.00 off')
                        ->scope('LINE_ITEM')
                        ->type('FIXED_AMOUNT')
                        ->uid('one-dollar-off')
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
            ->id('CAISENgvlJ6jLWAzERDzjyHVybY')
            ->lineItems(
                [
                    OrderLineItemBuilder::init(
                        '1'
                    )
                        ->appliedDiscounts(
                            [
                                OrderLineItemAppliedDiscountBuilder::init(
                                    'membership-discount'
                                )
                                    ->appliedMoney(
                                        MoneyBuilder::init()
                                            ->amount(8)
                                            ->currency('USD')
                                            ->build()
                                    )
                                    ->uid('jWdgP1TpHPFBuVrz81mXVC')
                                    ->build(),
                                OrderLineItemAppliedDiscountBuilder::init(
                                    'labor-day-sale'
                                )
                                    ->appliedMoney(
                                        MoneyBuilder::init()
                                            ->amount(79)
                                            ->currency('USD')
                                            ->build()
                                    )
                                    ->uid('jnZOjjVY57eRcQAVgEwFuC')
                                    ->build()
                            ]
                        )
                        ->appliedTaxes(
                            [
                                OrderLineItemAppliedTaxBuilder::init(
                                    'state-sales-tax'
                                )
                                    ->appliedMoney(
                                        MoneyBuilder::init()
                                            ->amount(136)
                                            ->currency('USD')
                                            ->build()
                                    )
                                    ->uid('aKG87ArnDpvMLSZJHxWUl')
                                    ->build()
                            ]
                        )
                        ->basePriceMoney(
                            MoneyBuilder::init()
                                ->amount(1599)
                                ->currency('USD')
                                ->build()
                        )
                        ->grossSalesMoney(
                            MoneyBuilder::init()
                                ->amount(1599)
                                ->currency('USD')
                                ->build()
                        )
                        ->name('New York Strip Steak')
                        ->totalDiscountMoney(
                            MoneyBuilder::init()
                                ->amount(87)
                                ->currency('USD')
                                ->build()
                        )
                        ->totalMoney(
                            MoneyBuilder::init()
                                ->amount(1648)
                                ->currency('USD')
                                ->build()
                        )
                        ->totalTaxMoney(
                            MoneyBuilder::init()
                                ->amount(136)
                                ->currency('USD')
                                ->build()
                        )
                        ->uid('8uSwfzvUImn3IRrvciqlXC')
                        ->variationTotalPriceMoney(
                            MoneyBuilder::init()
                                ->amount(1599)
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
                                    'membership-discount'
                                )
                                    ->appliedMoney(
                                        MoneyBuilder::init()
                                            ->amount(22)
                                            ->currency('USD')
                                            ->build()
                                    )
                                    ->uid('nUXvdsIItfKko0dbYtY58C')
                                    ->build(),
                                OrderLineItemAppliedDiscountBuilder::init(
                                    'labor-day-sale'
                                )
                                    ->appliedMoney(
                                        MoneyBuilder::init()
                                            ->amount(224)
                                            ->currency('USD')
                                            ->build()
                                    )
                                    ->uid('qSdkOOOernlVQqsJ94SPjB')
                                    ->build(),
                                OrderLineItemAppliedDiscountBuilder::init(
                                    'one-dollar-off'
                                )
                                    ->appliedMoney(
                                        MoneyBuilder::init()
                                            ->amount(100)
                                            ->currency('USD')
                                            ->build()
                                    )
                                    ->uid('y7bVl4njrWAnfDwmz19izB')
                                    ->build()
                            ]
                        )
                        ->appliedTaxes(
                            [
                                OrderLineItemAppliedTaxBuilder::init(
                                    'state-sales-tax'
                                )
                                    ->appliedMoney(
                                        MoneyBuilder::init()
                                            ->amount(374)
                                            ->currency('USD')
                                            ->build()
                                    )
                                    ->uid('v1dAgrfUVUPTnVTf9sRPz')
                                    ->build()
                            ]
                        )
                        ->basePriceMoney(
                            MoneyBuilder::init()
                                ->amount(2200)
                                ->currency('USD')
                                ->build()
                        )
                        ->catalogObjectId('BEMYCSMIJL46OCDV4KYIKXIB')
                        ->grossSalesMoney(
                            MoneyBuilder::init()
                                ->amount(4500)
                                ->currency('USD')
                                ->build()
                        )
                        ->modifiers(
                            [
                                OrderLineItemModifierBuilder::init()
                                    ->basePriceMoney(
                                        MoneyBuilder::init()
                                            ->amount(50)
                                            ->currency('USD')
                                            ->build()
                                    )
                                    ->catalogObjectId('CHQX7Y4KY6N5KINJKZCFURPZ')
                                    ->name('Well')
                                    ->totalPriceMoney(
                                        MoneyBuilder::init()
                                            ->amount(100)
                                            ->currency('USD')
                                            ->build()
                                    )
                                    ->uid('Lo3qMMckDluu9Qsb58d4CC')
                                    ->build()
                            ]
                        )
                        ->name('New York Steak')
                        ->totalDiscountMoney(
                            MoneyBuilder::init()
                                ->amount(346)
                                ->currency('USD')
                                ->build()
                        )
                        ->totalMoney(
                            MoneyBuilder::init()
                                ->amount(4528)
                                ->currency('USD')
                                ->build()
                        )
                        ->totalTaxMoney(
                            MoneyBuilder::init()
                                ->amount(374)
                                ->currency('USD')
                                ->build()
                        )
                        ->uid('v8ZuEXpOJpb0bazLuvrLDB')
                        ->variationName('Larger')
                        ->variationTotalPriceMoney(
                            MoneyBuilder::init()
                                ->amount(4400)
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
                            ->amount(433)
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
                            ->amount(510)
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
                            ->amount(6176)
                            ->currency('USD')
                            ->build()
                    )
                    ->build()
            )
            ->referenceId('my-order-001')
            ->source(
                OrderSourceBuilder::init()
                    ->name('My App')
                    ->build()
            )
            ->state('OPEN')
            ->taxes(
                [
                    OrderLineItemTaxBuilder::init()
                        ->appliedMoney(
                            MoneyBuilder::init()
                                ->amount(510)
                                ->currency('USD')
                                ->build()
                        )
                        ->name('State Sales Tax')
                        ->percentage('9')
                        ->scope('ORDER')
                        ->type('ADDITIVE')
                        ->uid('state-sales-tax')
                        ->build()
                ]
            )
            ->totalDiscountMoney(
                MoneyBuilder::init()
                    ->amount(433)
                    ->currency('USD')
                    ->build()
            )
            ->totalMoney(
                MoneyBuilder::init()
                    ->amount(6176)
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
                    ->amount(510)
                    ->currency('USD')
                    ->build()
            )
            ->totalTipMoney(
                MoneyBuilder::init()
                    ->amount(0)
                    ->currency('USD')
                    ->build()
            )
            ->updatedAt('2020-01-17T20:47:53.293Z')
            ->version(1)
            ->build()
    )
    ->build();
```

