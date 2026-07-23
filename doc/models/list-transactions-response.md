
# List Transactions Response

Defines the fields that are included in the response body of
a request to the [ListTransactions](https://developer.squareup.com/reference/square_2021-08-18/transactions-api/list-transactions) endpoint.

One of `errors` or `transactions` is present in a given response (never both).

## Structure

`ListTransactionsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cursor` | `?string` | Optional | A pagination cursor for retrieving the next set of results,<br>if any remain. Provide this value as the `cursor` parameter in a subsequent<br>request to this endpoint.<br><br>See [Paginating results](https://developer.squareup.com/docs/working-with-apis/pagination) for more information. | getCursor(): ?string | setCursor(?string cursor): void |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `transactions` | [`?(Transaction[])`](../../doc/models/transaction.md) | Optional | An array of transactions that match your query. | getTransactions(): ?array | setTransactions(?array transactions): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\ListTransactionsResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\TransactionBuilder;
use SquareConnectAPILib\Models\Builders\RefundBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;
use SquareConnectAPILib\Models\Builders\AdditionalRecipientBuilder;
use SquareConnectAPILib\Models\Builders\TenderBuilder;
use SquareConnectAPILib\Models\Builders\TenderCardDetailsBuilder;
use SquareConnectAPILib\Models\Builders\CardBuilder;

$listTransactionsResponse = ListTransactionsResponseBuilder::init()
    ->cursor('cursor4')
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
    ->transactions(
        [
            TransactionBuilder::init()
                ->clientId('client_id0')
                ->createdAt('2016-01-20T22:57:56Z')
                ->id('KnL67ZIwXCPtzOrqj0HrkxMF')
                ->locationId('18YC4JDH91E1H')
                ->orderId('order_id2')
                ->product('EXTERNAL_API')
                ->referenceId('some optional reference id')
                ->refunds(
                    [
                        RefundBuilder::init(
                            MoneyBuilder::init()
                                ->amount(5000)
                                ->currency('USD')
                                ->build(),
                            '7a5RcVI0CxbOcJ2wMOkE',
                            '18YC4JDH91E1H',
                            'some reason why',
                            'APPROVED',
                            'MtZRYYdDrYNQbOvV7nbuBvMF',
                            'KnL67ZIwXCPtzOrqj0HrkxMF'
                        )
                            ->additionalRecipients(
                                [
                                    AdditionalRecipientBuilder::init(
                                        MoneyBuilder::init()
                                            ->amount(100)
                                            ->currency('USD')
                                            ->build(),
                                        '057P5VYJ4A5X1'
                                    )
                                        ->description('Application fees')
                                        ->build()
                                ]
                            )
                            ->createdAt('2016-01-20T22:59:20Z')
                            ->processingFeeMoney(
                                MoneyBuilder::init()
                                    ->amount(138)
                                    ->currency('USD')
                                    ->build()
                            )
                            ->build()
                    ]
                )
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
                                        ->build()
                                ]
                            )
                            ->amountMoney(
                                MoneyBuilder::init()
                                    ->amount(5000)
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
                            ->createdAt('2016-01-20T22:57:56Z')
                            ->id('MtZRYYdDrYNQbOvV7nbuBvMF')
                            ->locationId('18YC4JDH91E1H')
                            ->note('some optional note')
                            ->processingFeeMoney(
                                MoneyBuilder::init()
                                    ->amount(138)
                                    ->currency('USD')
                                    ->build()
                            )
                            ->transactionId('KnL67ZIwXCPtzOrqj0HrkxMF')
                            ->build()
                    ]
                )
                ->build()
        ]
    )
    ->build();
```

