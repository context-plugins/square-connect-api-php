
# List Payments Response

Defines the response returned by [ListPayments](https://developer.squareup.com/reference/square_2021-08-18/payments-api/list-payments).

## Structure

`ListPaymentsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cursor` | `?string` | Optional | The pagination cursor to be used in a subsequent request. If empty,<br>this is the final response.<br><br>For more information, see [Pagination](https://developer.squareup.com/docs/basics/api101/pagination). | getCursor(): ?string | setCursor(?string cursor): void |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Information about errors encountered during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `payments` | [`?(Payment[])`](../../doc/models/payment.md) | Optional | The requested list of payments. | getPayments(): ?array | setPayments(?array payments): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\ListPaymentsResponseBuilder;
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

$listPaymentsResponse = ListPaymentsResponseBuilder::init()
    ->cursor('2TTnuq0yRYDdBRSFF2XuFkgO1Bclt4ZHNI7YrFNeyZ6rL1WZXkdnLn10H8fBIwFKdKW1Af6ifRa')
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
    ->payments(
        [
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
                        ->authResultCode('NQbV3A')
                        ->avsStatus('AVS_ACCEPTED')
                        ->card(
                            CardBuilder::init()
                                ->cardBrand('VISA')
                                ->expMonth(2)
                                ->expYear(2022)
                                ->fingerprint('sq-1-lHpUJIUyqOPQmH89b6GuQEljmc-mZmu4kSTaMlkLDkJI7NVjAl4Zirn2sk3OeyVKVA')
                                ->last4('1111')
                                ->build()
                        )
                        ->cardPaymentTimeline(
                            CardPaymentTimelineBuilder::init()
                                ->authorizedAt('2019-07-09T14:36:13.798Z')
                                ->build()
                        )
                        ->cvvStatus('CVV_ACCEPTED')
                        ->entryMethod('KEYED')
                        ->status('AUTHORIZED')
                        ->build()
                )
                ->createdAt('2019-07-09T14:36:13.745Z')
                ->id('ifrBnAil7rRfDtd27cdf9g9WO8paB')
                ->locationId('QLIJX16Q3UZ0A')
                ->orderId('MvfIilKnIYKBium4rauH67wFzRxv')
                ->sourceType('CARD')
                ->status('APPROVED')
                ->totalMoney(
                    MoneyBuilder::init()
                        ->amount(1000)
                        ->currency('USD')
                        ->build()
                )
                ->updatedAt('2019-07-09T14:36:13.883Z')
                ->versionToken('v6orqdHcW2TwuzCQRdF6a4ktbG8T8nbDcBx8eyrkoZl6o')
                ->build(),
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
                ->cardDetails(
                    CardPaymentDetailsBuilder::init()
                        ->authResultCode('vPIr0K')
                        ->avsStatus('AVS_ACCEPTED')
                        ->card(
                            CardBuilder::init()
                                ->cardBrand('VISA')
                                ->expMonth(7)
                                ->expYear(2026)
                                ->fingerprint('sq-1-TpmjbNBMFdibiIjpQI5LiRgNUBC7u1689i0TgHjnlyHEWYB7tnn-K4QbW4ttvtaqXw')
                                ->last4('2796')
                                ->build()
                        )
                        ->cardPaymentTimeline(
                            CardPaymentTimelineBuilder::init()
                                ->authorizedAt('2019-07-08T01:00:51.617Z')
                                ->capturedAt('2019-07-08T01:13:58.508Z')
                                ->build()
                        )
                        ->cvvStatus('CVV_ACCEPTED')
                        ->entryMethod('ON_FILE')
                        ->status('CAPTURED')
                        ->build()
                )
                ->createdAt('2019-07-08T01:00:51.607Z')
                ->customerId('RDX9Z4XTIZR7MRZJUXNY9HUK6I')
                ->id('GQTFp1ZlXdpoW4o6eGiZhbjosiDFf')
                ->locationId('XTI0H92143A39')
                ->orderId('m2Hr8Hk8A3CTyQQ1k4ynExg92tO3')
                ->processingFee(
                    [
                        ProcessingFeeBuilder::init()
                            ->amountMoney(
                                MoneyBuilder::init()
                                    ->amount(59)
                                    ->currency('USD')
                                    ->build()
                            )
                            ->effectiveAt('2019-07-08T03:00:53.000Z')
                            ->type('INITIAL')
                            ->build()
                    ]
                )
                ->sourceType('CARD')
                ->status('COMPLETED')
                ->totalMoney(
                    MoneyBuilder::init()
                        ->amount(1000)
                        ->currency('USD')
                        ->build()
                )
                ->updatedAt('2019-07-08T01:13:58.508Z')
                ->versionToken('pE0wanQBErcnO4ubL49pHCV1yAs4BUScWXb8fVvkRqa6o')
                ->build()
        ]
    )
    ->build();
```

