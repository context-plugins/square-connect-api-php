
# V1 List Settlements Response

## Structure

`V1ListSettlementsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `items` | [`?(V1Settlement[])`](../../doc/models/v1-settlement.md) | Optional | - | getItems(): ?array | setItems(?array items): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\V1ListSettlementsResponseBuilder;
use SquareConnectAPILib\Models\Builders\V1SettlementBuilder;
use SquareConnectAPILib\Models\Builders\V1SettlementEntryBuilder;
use SquareConnectAPILib\Models\Builders\V1MoneyBuilder;

$v1ListSettlementsResponse = V1ListSettlementsResponseBuilder::init()
    ->items(
        [
            V1SettlementBuilder::init()
                ->bankAccountId('bank_account_id8')
                ->entries(
                    [
                        V1SettlementEntryBuilder::init()
                            ->amountMoney(
                                V1MoneyBuilder::init()
                                    ->amount(186)
                                    ->currencyCode('currency_code4')
                                    ->build()
                            )
                            ->feeMoney(
                                V1MoneyBuilder::init()
                                    ->amount(108)
                                    ->currencyCode('currency_code6')
                                    ->build()
                            )
                            ->paymentId('payment_id0')
                            ->type('type0')
                            ->build(),
                        V1SettlementEntryBuilder::init()
                            ->amountMoney(
                                V1MoneyBuilder::init()
                                    ->amount(186)
                                    ->currencyCode('currency_code4')
                                    ->build()
                            )
                            ->feeMoney(
                                V1MoneyBuilder::init()
                                    ->amount(108)
                                    ->currencyCode('currency_code6')
                                    ->build()
                            )
                            ->paymentId('payment_id0')
                            ->type('type0')
                            ->build(),
                        V1SettlementEntryBuilder::init()
                            ->amountMoney(
                                V1MoneyBuilder::init()
                                    ->amount(186)
                                    ->currencyCode('currency_code4')
                                    ->build()
                            )
                            ->feeMoney(
                                V1MoneyBuilder::init()
                                    ->amount(108)
                                    ->currencyCode('currency_code6')
                                    ->build()
                            )
                            ->paymentId('payment_id0')
                            ->type('type0')
                            ->build()
                    ]
                )
                ->id('id8')
                ->initiatedAt('initiated_at0')
                ->status('status0')
                ->build()
        ]
    )
    ->build();
```

