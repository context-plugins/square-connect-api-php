
# Create Checkout Response

Defines the fields that are included in the response body of
a request to the `CreateCheckout` endpoint.

## Structure

`CreateCheckoutResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `checkout` | [`?Checkout`](../../doc/models/checkout.md) | Optional | Square Checkout lets merchants accept online payments for supported<br>payment types using a checkout workflow hosted on squareup.com. | getCheckout(): ?Checkout | setCheckout(?Checkout checkout): void |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CreateCheckoutResponseBuilder;
use SquareConnectAPILib\Models\Builders\CheckoutBuilder;
use SquareConnectAPILib\Models\Builders\AdditionalRecipientBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;
use SquareConnectAPILib\Models\Builders\OrderBuilder;
use SquareConnectAPILib\Models\Builders\OrderLineItemDiscountBuilder;
use SquareConnectAPILib\Models\Builders\AddressBuilder;
use SquareConnectAPILib\Models\Builders\OrderLineItemBuilder;
use SquareConnectAPILib\Models\Builders\OrderLineItemAppliedDiscountBuilder;
use SquareConnectAPILib\Models\Builders\OrderLineItemAppliedTaxBuilder;
use SquareConnectAPILib\Models\Builders\OrderLineItemTaxBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;

$createCheckoutResponse = CreateCheckoutResponseBuilder::init()
    ->checkout(
        CheckoutBuilder::init()
            ->additionalRecipients(
                [
                    AdditionalRecipientBuilder::init(
                        MoneyBuilder::init()
                            ->amount(60)
                            ->currency('USD')
                            ->build(),
                        '057P5VYJ4A5X1'
                    )
                        ->description('Application fees')
                        ->receivableId('receivable_id6')
                        ->build()
                ]
            )
            ->askForShippingAddress(true)
            ->checkoutPageUrl('https://connect.squareup.com/v2/checkout?c=CAISEHGimXh-C3RIT4og1a6u1qw&l=CYTKRM7R7JMV8')
            ->createdAt('2017-06-16T22:25:35Z')
            ->id('CAISEHGimXh-C3RIT4og1a6u1qw')
            ->merchantSupportEmail('merchant+support@website.com')
            ->order(
                OrderBuilder::init(
                    'location_id'
                )
                    ->customerId('customer_id')
                    ->discounts(
                        [
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
                                ->scope('LINE_ITEM')
                                ->type('FIXED_AMOUNT')
                                ->uid('56ae1696-z1e3-9328-af6d-f1e04d947gd4')
                                ->build()
                        ]
                    )
                    ->lineItems(
                        [
                            OrderLineItemBuilder::init(
                                '2'
                            )
                                ->appliedDiscounts(
                                    [
                                        OrderLineItemAppliedDiscountBuilder::init(
                                            '56ae1696-z1e3-9328-af6d-f1e04d947gd4'
                                        )
                                            ->appliedMoney(
                                                MoneyBuilder::init()
                                                    ->amount(100)
                                                    ->currency('USD')
                                                    ->build()
                                            )
                                            ->build()
                                    ]
                                )
                                ->appliedTaxes(
                                    [
                                        OrderLineItemAppliedTaxBuilder::init(
                                            '38ze1696-z1e3-5628-af6d-f1e04d947fg3'
                                        )
                                            ->appliedMoney(
                                                MoneyBuilder::init()
                                                    ->amount(103)
                                                    ->currency('USD')
                                                    ->build()
                                            )
                                            ->build()
                                    ]
                                )
                                ->basePriceMoney(
                                    MoneyBuilder::init()
                                        ->amount(1500)
                                        ->currency('USD')
                                        ->build()
                                )
                                ->name('Printed T Shirt')
                                ->totalDiscountMoney(
                                    MoneyBuilder::init()
                                        ->amount(100)
                                        ->currency('USD')
                                        ->build()
                                )
                                ->totalMoney(
                                    MoneyBuilder::init()
                                        ->amount(1503)
                                        ->currency('USD')
                                        ->build()
                                )
                                ->totalTaxMoney(
                                    MoneyBuilder::init()
                                        ->amount(103)
                                        ->currency('USD')
                                        ->build()
                                )
                                ->build(),
                            OrderLineItemBuilder::init(
                                '1'
                            )
                                ->basePriceMoney(
                                    MoneyBuilder::init()
                                        ->amount(2500)
                                        ->currency('USD')
                                        ->build()
                                )
                                ->name('Slim Jeans')
                                ->totalMoney(
                                    MoneyBuilder::init()
                                        ->amount(2500)
                                        ->currency('USD')
                                        ->build()
                                )
                                ->build(),
                            OrderLineItemBuilder::init(
                                '3'
                            )
                                ->basePriceMoney(
                                    MoneyBuilder::init()
                                        ->amount(3500)
                                        ->currency('USD')
                                        ->build()
                                )
                                ->name('Woven Sweater')
                                ->totalMoney(
                                    MoneyBuilder::init()
                                        ->amount(10500)
                                        ->currency('USD')
                                        ->build()
                                )
                                ->build()
                        ]
                    )
                    ->referenceId('reference_id')
                    ->taxes(
                        [
                            OrderLineItemTaxBuilder::init()
                                ->percentage('7.75')
                                ->scope('LINE_ITEM')
                                ->type('INCLUSIVE')
                                ->uid('38ze1696-z1e3-5628-af6d-f1e04d947fg3')
                                ->build()
                        ]
                    )
                    ->totalDiscountMoney(
                        MoneyBuilder::init()
                            ->amount(100)
                            ->currency('USD')
                            ->build()
                    )
                    ->totalMoney(
                        MoneyBuilder::init()
                            ->amount(14503)
                            ->currency('USD')
                            ->build()
                    )
                    ->totalTaxMoney(
                        MoneyBuilder::init()
                            ->amount(103)
                            ->currency('USD')
                            ->build()
                    )
                    ->build()
            )
            ->prePopulateBuyerEmail('example@email.com')
            ->prePopulateShippingAddress(
                AddressBuilder::init()
                    ->addressLine1('1455 Market St.')
                    ->addressLine2('Suite 600')
                    ->administrativeDistrictLevel1('CA')
                    ->country('US')
                    ->firstName('Jane')
                    ->lastName('Doe')
                    ->locality('San Francisco')
                    ->postalCode('94103')
                    ->build()
            )
            ->redirectUrl('https://merchant.website.com/order-confirm')
            ->build()
    )
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
    ->build();
```

