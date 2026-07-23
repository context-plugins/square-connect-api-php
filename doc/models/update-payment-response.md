
# Update Payment Response

Defines the response returned by
[UpdatePayment](https://developer.squareup.com/reference/square_2021-08-18/payments-api/update-payment).

## Structure

`UpdatePaymentResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `payment` | [`?Payment`](../../doc/models/payment.md) | Optional | Represents a payment processed by the Square API. | getPayment(): ?Payment | setPayment(?Payment payment): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\UpdatePaymentResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\PaymentBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;
use SquareConnectAPILib\Models\Builders\BankAccountPaymentDetailsBuilder;
use SquareConnectAPILib\Models\Builders\ACHDetailsBuilder;
use SquareConnectAPILib\Models\Builders\AddressBuilder;
use SquareConnectAPILib\Models\Builders\CardPaymentDetailsBuilder;
use SquareConnectAPILib\Models\Builders\CardBuilder;
use SquareConnectAPILib\Models\Builders\CardPaymentTimelineBuilder;

$updatePaymentResponse = UpdatePaymentResponseBuilder::init()
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
    ->payment(
        PaymentBuilder::init()
            ->amountMoney(
                MoneyBuilder::init()
                    ->amount(1000)
                    ->currency('USD')
                    ->build()
            )
            ->appFeeMoney(
                MoneyBuilder::init()
                    ->amount(106)
                    ->currency('currency4')
                    ->build()
            )
            ->approvedMoney(
                MoneyBuilder::init()
                    ->amount(1000)
                    ->currency('USD')
                    ->build()
            )
            ->bankAccountDetails(
                BankAccountPaymentDetailsBuilder::init()
                    ->accountOwnershipType('account_ownership_type8')
                    ->achDetails(
                        ACHDetailsBuilder::init()
                            ->accountNumberSuffix('account_number_suffix2')
                            ->accountType('account_type2')
                            ->routingNumber('routing_number0')
                            ->build()
                    )
                    ->bankName('bank_name4')
                    ->country('country4')
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
                    ->build()
            )
            ->billingAddress(
                AddressBuilder::init()
                    ->addressLine1('address_line_12')
                    ->addressLine2('address_line_28')
                    ->addressLine3('address_line_34')
                    ->administrativeDistrictLevel1('administrative_district_level_12')
                    ->administrativeDistrictLevel2('administrative_district_level_26')
                    ->build()
            )
            ->capabilities(
                [
                    'EDIT_AMOUNT_UP',
                    'EDIT_AMOUNT_DOWN',
                    'EDIT_TIP_AMOUNT_UP',
                    'EDIT_TIP_AMOUNT_DOWN'
                ]
            )
            ->cardDetails(
                CardPaymentDetailsBuilder::init()
                    ->authResultCode('ajM2ZF')
                    ->avsStatus('AVS_ACCEPTED')
                    ->card(
                        CardBuilder::init()
                            ->bin('411111')
                            ->cardBrand('VISA')
                            ->cardType('CREDIT')
                            ->expMonth(2)
                            ->expYear(2022)
                            ->fingerprint('sq-1-n_BL15KP87ClDa4-h2nXOI0fp5VnxNH6hfhzqhptTfAgxgLuGFcg6jIPngDz4IkkTQ')
                            ->last4('1111')
                            ->build()
                    )
                    ->cardPaymentTimeline(
                        CardPaymentTimelineBuilder::init()
                            ->authorizedAt('2021-02-24T03:33:43.681Z')
                            ->build()
                    )
                    ->cvvStatus('CVV_ACCEPTED')
                    ->entryMethod('KEYED')
                    ->statementDescription('SQ *MY BUSINESS GOSQ.COM')
                    ->status('AUTHORIZED')
                    ->build()
            )
            ->createdAt('2021-03-02T19:53:31.055Z')
            ->delayAction('CANCEL')
            ->delayDuration('PT168H')
            ->delayedUntil('2021-03-09T19:53:31.055Z')
            ->id('XllelosAAfmkf9mOa0YB4PqSZACZY')
            ->locationId('XTI0H92143A39')
            ->orderId('B6qiKWus1d3TBoN2Qn5kfDiWZlfZY')
            ->receiptNumber('Xlle')
            ->sourceType('CARD')
            ->status('APPROVED')
            ->tipMoney(
                MoneyBuilder::init()
                    ->amount(300)
                    ->currency('USD')
                    ->build()
            )
            ->totalMoney(
                MoneyBuilder::init()
                    ->amount(1300)
                    ->currency('USD')
                    ->build()
            )
            ->updatedAt('2021-03-02T19:53:31.164Z')
            ->versionToken('9TKsTawsWZvdZZD5uhAZFWfd3chxFXB49cgFpD2Kujf6o')
            ->build()
    )
    ->build();
```

