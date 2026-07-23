
# Get Payment Response

Defines the response returned by [GetPayment](https://developer.squareup.com/reference/square_2021-08-18/payments-api/get-payment).

## Structure

`GetPaymentResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Information about errors encountered during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `payment` | [`?Payment`](../../doc/models/payment.md) | Optional | Represents a payment processed by the Square API. | getPayment(): ?Payment | setPayment(?Payment payment): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\GetPaymentResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\PaymentBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;
use SquareConnectAPILib\Models\Builders\BankAccountPaymentDetailsBuilder;
use SquareConnectAPILib\Models\Builders\ACHDetailsBuilder;
use SquareConnectAPILib\Models\Builders\AddressBuilder;
use SquareConnectAPILib\Models\Builders\CardPaymentDetailsBuilder;
use SquareConnectAPILib\Models\Builders\CardBuilder;
use SquareConnectAPILib\Models\Builders\CardPaymentTimelineBuilder;
use SquareConnectAPILib\Models\Builders\ProcessingFeeBuilder;

$getPaymentResponse = GetPaymentResponseBuilder::init()
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
    ->payment(
        PaymentBuilder::init()
            ->amountMoney(
                MoneyBuilder::init()
                    ->amount(200)
                    ->currency('USD')
                    ->build()
            )
            ->appFeeMoney(
                MoneyBuilder::init()
                    ->amount(10)
                    ->currency('USD')
                    ->build()
            )
            ->approvedMoney(
                MoneyBuilder::init()
                    ->amount(200)
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
            ->cardDetails(
                CardPaymentDetailsBuilder::init()
                    ->authResultCode('nsAyY2')
                    ->avsStatus('AVS_ACCEPTED')
                    ->card(
                        CardBuilder::init()
                            ->bin('411111')
                            ->cardBrand('VISA')
                            ->cardType('DEBIT')
                            ->expMonth(7)
                            ->expYear(2026)
                            ->fingerprint('sq-1-TpmjbNBMFdibiIjpQI5LiRgNUBC7u1689i0TgHjnlyHEWYB7tnn-K4QbW4ttvtaqXw')
                            ->last4('1111')
                            ->prepaidType('PREPAID')
                            ->build()
                    )
                    ->cardPaymentTimeline(
                        CardPaymentTimelineBuilder::init()
                            ->authorizedAt('2019-07-10T13:23:49.234Z')
                            ->capturedAt('2019-07-10T13:23:49.446Z')
                            ->build()
                    )
                    ->cvvStatus('CVV_ACCEPTED')
                    ->entryMethod('ON_FILE')
                    ->statementDescription('SQ *MY MERCHANT')
                    ->status('CAPTURED')
                    ->build()
            )
            ->createdAt('2019-07-10T13:23:49.154Z')
            ->customerId('RDX9Z4XTIZR7MRZJUXNY9HUK6I')
            ->id('GQTFp1ZlXdpoW4o6eGiZhbjosiDFf')
            ->locationId('XTI0H92143A39')
            ->note('Brief description')
            ->orderId('m2Hr8Hk8A3CTyQQ1k4ynExg92tO3')
            ->processingFee(
                [
                    ProcessingFeeBuilder::init()
                        ->amountMoney(
                            MoneyBuilder::init()
                                ->amount(36)
                                ->currency('USD')
                                ->build()
                        )
                        ->effectiveAt('2019-07-10T15:23:49.000Z')
                        ->type('INITIAL')
                        ->build()
                ]
            )
            ->receiptNumber('GQTF')
            ->receiptUrl('https://squareup.com/receipt/preview/GQTFp1ZlXdpoW4o6eGiZhbjosiDFf')
            ->referenceId('123456')
            ->sourceType('CARD')
            ->status('COMPLETED')
            ->totalMoney(
                MoneyBuilder::init()
                    ->amount(200)
                    ->currency('USD')
                    ->build()
            )
            ->updatedAt('2019-07-10T13:23:49.446Z')
            ->versionToken('hj8JqHWu9R1Kkfu63UuIUmYc7zm6YFOt92g8d2fb9fz6o')
            ->build()
    )
    ->build();
```

