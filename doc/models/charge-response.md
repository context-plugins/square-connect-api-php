
# Charge Response

Defines the fields that are included in the response body of
a request to the [Charge](https://developer.squareup.com/reference/square_2021-08-18/transactions-api/charge) endpoint.

One of `errors` or `transaction` is present in a given response (never both).

## Structure

`ChargeResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `transaction` | [`?Transaction`](../../doc/models/transaction.md) | Optional | Represents a transaction processed with Square, either with the<br>Connect API or with Square Point of Sale.<br><br>The `tenders` field of this object lists all methods of payment used to pay in<br>the transaction. | getTransaction(): ?Transaction | setTransaction(?Transaction transaction): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\ChargeResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\TransactionBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;
use SquareConnectAPILib\Models\Builders\AdditionalRecipientBuilder;
use SquareConnectAPILib\Models\Builders\TenderBuilder;
use SquareConnectAPILib\Models\Builders\TenderCardDetailsBuilder;
use SquareConnectAPILib\Models\Builders\CardBuilder;

$chargeResponse = ChargeResponseBuilder::init()
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
    ->transaction(
        TransactionBuilder::init()
            ->clientId('client_id0')
            ->createdAt('2016-03-10T22:57:56Z')
            ->id('KnL67ZIwXCPtzOrqj0HrkxMF')
            ->locationId('18YC4JDH91E1H')
            ->orderId('order_id2')
            ->product('EXTERNAL_API')
            ->referenceId('some optional reference id')
            ->tenders(
                [
                    TenderBuilder::init(
                        'CARD'
                    )
                        ->additionalRecipients(
                            [
                                AdditionalRecipientBuilder::init(
                                    MoneyBuilder::init()
                                        ->amount(20)
                                        ->currency('USD')
                                        ->build(),
                                    '057P5VYJ4A5X1'
                                )
                                    ->description('Application fees')
                                    ->receivableId('ISu5xwxJ5v0CMJTQq7RvqyMF')
                                    ->build()
                            ]
                        )
                        ->amountMoney(
                            MoneyBuilder::init()
                                ->amount(200)
                                ->currency('USD')
                                ->build()
                        )
                        ->cardDetails(
                            TenderCardDetailsBuilder::init()
                                ->card(
                                    CardBuilder::init()
                                        ->cardBrand('VISA')
                                        ->last4('1111')
                                        ->build()
                                )
                                ->entryMethod('KEYED')
                                ->status('CAPTURED')
                                ->build()
                        )
                        ->createdAt('2016-03-10T22:57:56Z')
                        ->id('MtZRYYdDrYNQbOvV7nbuBvMF')
                        ->locationId('18YC4JDH91E1H')
                        ->note('some optional note')
                        ->transactionId('KnL67ZIwXCPtzOrqj0HrkxMF')
                        ->build()
                ]
            )
            ->build()
    )
    ->build();
```

