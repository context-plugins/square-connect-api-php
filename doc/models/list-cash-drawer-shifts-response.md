
# List Cash Drawer Shifts Response

## Structure

`ListCashDrawerShiftsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cursor` | `?string` | Optional | Opaque cursor for fetching the next page of results. Cursor is not<br>present in the last page of results. | getCursor(): ?string | setCursor(?string cursor): void |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `items` | [`?(CashDrawerShiftSummary[])`](../../doc/models/cash-drawer-shift-summary.md) | Optional | A collection of CashDrawerShiftSummary objects for shifts that match<br>the query. | getItems(): ?array | setItems(?array items): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\ListCashDrawerShiftsResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\CashDrawerShiftSummaryBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;

$listCashDrawerShiftsResponse = ListCashDrawerShiftsResponseBuilder::init()
    ->cursor('cursor0')
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
    ->items(
        [
            CashDrawerShiftSummaryBuilder::init()
                ->closedAt('2019-11-22T00:44:49.000Z')
                ->closedCashMoney(
                    MoneyBuilder::init()
                        ->amount(9970)
                        ->currency('USD')
                        ->build()
                )
                ->description('Misplaced some change')
                ->endedAt('2019-11-22T00:44:49.000Z')
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
                ->state('CLOSED')
                ->build()
        ]
    )
    ->build();
```

