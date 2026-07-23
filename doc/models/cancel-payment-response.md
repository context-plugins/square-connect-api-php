
# Cancel Payment Response

Defines the response returned by [CancelPayment](https://developer.squareup.com/reference/square_2021-08-18/payments-api/cancel-payment).

## Structure

`CancelPaymentResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Information about errors encountered during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `payment` | [`?Payment`](../../doc/models/payment.md) | Optional | Represents a payment processed by the Square API. | getPayment(): ?Payment | setPayment(?Payment payment): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CancelPaymentResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\PaymentBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;
use SquareConnectAPILib\Models\Builders\BankAccountPaymentDetailsBuilder;
use SquareConnectAPILib\Models\Builders\ACHDetailsBuilder;
use SquareConnectAPILib\Models\Builders\AddressBuilder;
use SquareConnectAPILib\Models\Builders\CardPaymentDetailsBuilder;
use SquareConnectAPILib\Models\Builders\CardBuilder;
use SquareConnectAPILib\Models\Builders\CardPaymentTimelineBuilder;

$cancelPaymentResponse = CancelPaymentResponseBuilder::init()
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
                    ->authResultCode('eWZBDh')
                    ->avsStatus('AVS_ACCEPTED')
                    ->card(
                        CardBuilder::init()
                            ->bin('411111')
                            ->cardBrand('VISA')
                            ->cardType('DEBIT')
                            ->expMonth(2)
                            ->expYear(2024)
                            ->fingerprint('sq-1-9PP0tWfcM6vIsYmfsesdjfhduHSDFNdJFNDfDNFjdfjpseirDErsaP')
                            ->last4('1234')
                            ->prepaidType('PREPAID')
                            ->build()
                    )
                    ->cardPaymentTimeline(
                        CardPaymentTimelineBuilder::init()
                            ->authorizedAt('2018-10-17T20:38:46.753Z')
                            ->voidedAt('2018-10-17T20:38:57.793Z')
                            ->build()
                    )
                    ->cvvStatus('CVV_ACCEPTED')
                    ->entryMethod('KEYED')
                    ->statementDescription('SQ *MY MERCHANT')
                    ->status('VOIDED')
                    ->build()
            )
            ->createdAt('2018-10-17T20:38:46.743Z')
            ->customerId('RDX9Z4XTIZR7MRZJUXNY9HUK6I')
            ->id('GQTFp1ZlXdpoW4o6eGiZhbjosiDFf')
            ->locationId('XTI0H92143A39')
            ->note('Brief description')
            ->orderId('m2Hr8Hk8A3CTyQQ1k4ynExg92tO3')
            ->referenceId('123456')
            ->sourceType('CARD')
            ->status('CANCELED')
            ->totalMoney(
                MoneyBuilder::init()
                    ->amount(200)
                    ->currency('USD')
                    ->build()
            )
            ->updatedAt('2018-10-17T20:38:57.693Z')
            ->versionToken('lAITJ6l8I8tFu62mCf2W4sxJQxN9FOaH5zwfsdPf7Dm6o')
            ->build()
    )
    ->build();
```

