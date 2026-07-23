
# Retrieve Cash Drawer Shift Response

## Structure

`RetrieveCashDrawerShiftResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cashDrawerShift` | [`?CashDrawerShift`](../../doc/models/cash-drawer-shift.md) | Optional | This model gives the details of a cash drawer shift.<br>The cash_payment_money, cash_refund_money, cash_paid_in_money,<br>and cash_paid_out_money fields are all computed by summing their respective<br>event types. | getCashDrawerShift(): ?CashDrawerShift | setCashDrawerShift(?CashDrawerShift cashDrawerShift): void |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\RetrieveCashDrawerShiftResponseBuilder;
use SquareConnectAPILib\Models\Builders\CashDrawerShiftBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;
use SquareConnectAPILib\Models\Builders\CashDrawerDeviceBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;

$retrieveCashDrawerShiftResponse = RetrieveCashDrawerShiftResponseBuilder::init()
    ->cashDrawerShift(
        CashDrawerShiftBuilder::init()
            ->cashPaidInMoney(
                MoneyBuilder::init()
                    ->amount(10000)
                    ->currency('USD')
                    ->build()
            )
            ->cashPaidOutMoney(
                MoneyBuilder::init()
                    ->amount(-10000)
                    ->currency('USD')
                    ->build()
            )
            ->cashPaymentMoney(
                MoneyBuilder::init()
                    ->amount(100)
                    ->currency('USD')
                    ->build()
            )
            ->cashRefundsMoney(
                MoneyBuilder::init()
                    ->amount(-100)
                    ->currency('USD')
                    ->build()
            )
            ->closedAt('2019-11-22T00:44:49.000Z')
            ->closedCashMoney(
                MoneyBuilder::init()
                    ->amount(9970)
                    ->currency('USD')
                    ->build()
            )
            ->closingEmployeeId('')
            ->description('Misplaced some change')
            ->device(
                CashDrawerDeviceBuilder::init()
                    ->name('My iPad')
                    ->build()
            )
            ->endedAt('2019-11-22T00:44:49.000Z')
            ->endingEmployeeId('')
            ->expectedCashMoney(
                MoneyBuilder::init()
                    ->amount(10000)
                    ->currency('USD')
                    ->build()
            )
            ->id('DCC99978-09A6-4926-849F-300BE9C5793A')
            ->openedAt('2019-11-22T00:42:54.000Z')
            ->openedCashMoney(
                MoneyBuilder::init()
                    ->amount(10000)
                    ->currency('USD')
                    ->build()
            )
            ->openingEmployeeId('')
            ->state('CLOSED')
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

