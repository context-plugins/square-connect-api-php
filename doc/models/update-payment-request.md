
# Update Payment Request

Describes a request to update a payment using
[UpdatePayment](https://developer.squareup.com/reference/square_2021-08-18/payments-api/update-payment).

## Structure

`UpdatePaymentRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `idempotencyKey` | `string` | Required | A unique string that identifies this `UpdatePayment` request. Keys can be any valid string<br>but must be unique for every `UpdatePayment` request.<br><br>The maximum is 45 characters.<br><br>For more information, see [Idempotency](https://developer.squareup.com/docs/basics/api101/idempotency).<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `45` | getIdempotencyKey(): string | setIdempotencyKey(string idempotencyKey): void |
| `payment` | [`?Payment`](../../doc/models/payment.md) | Optional | Represents a payment processed by the Square API. | getPayment(): ?Payment | setPayment(?Payment payment): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\UpdatePaymentRequestBuilder;
use SquareConnectAPILib\Models\Builders\PaymentBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;
use SquareConnectAPILib\Models\Builders\BankAccountPaymentDetailsBuilder;
use SquareConnectAPILib\Models\Builders\ACHDetailsBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\AddressBuilder;

$updatePaymentRequest = UpdatePaymentRequestBuilder::init(
    'idempotency_key4'
)
    ->payment(
        PaymentBuilder::init()
            ->amountMoney(
                MoneyBuilder::init()
                    ->amount(186)
                    ->currency('currency8')
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
                    ->amount(138)
                    ->currency('currency2')
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
            ->build()
    )
    ->build();
```

