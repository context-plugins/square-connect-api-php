
# V1 Settlement

V1Settlement

## Structure

`V1Settlement`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `bankAccountId` | `?string` | Optional | The Square-issued unique identifier for the bank account associated with the settlement. | getBankAccountId(): ?string | setBankAccountId(?string bankAccountId): void |
| `entries` | [`?(V1SettlementEntry[])`](../../doc/models/v1-settlement-entry.md) | Optional | The entries included in this settlement. | getEntries(): ?array | setEntries(?array entries): void |
| `id` | `?string` | Optional | The settlement's unique identifier. | getId(): ?string | setId(?string id): void |
| `initiatedAt` | `?string` | Optional | The time when the settlement was submitted for deposit or withdrawal, in ISO 8601 format. | getInitiatedAt(): ?string | setInitiatedAt(?string initiatedAt): void |
| `status` | `?string` | Optional | The settlement's current status. | getStatus(): ?string | setStatus(?string status): void |
| `totalMoney` | [`?V1Money`](../../doc/models/v1-money.md) | Optional | - | getTotalMoney(): ?V1Money | setTotalMoney(?V1Money totalMoney): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\V1SettlementBuilder;
use SquareConnectAPILib\Models\Builders\V1SettlementEntryBuilder;
use SquareConnectAPILib\Models\Builders\V1MoneyBuilder;

$v1Settlement = V1SettlementBuilder::init()
    ->bankAccountId('bank_account_id4')
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
                ->build()
        ]
    )
    ->id('id4')
    ->initiatedAt('initiated_at6')
    ->status('status6')
    ->build();
```

