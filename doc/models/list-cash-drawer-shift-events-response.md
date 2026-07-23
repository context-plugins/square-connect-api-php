
# List Cash Drawer Shift Events Response

## Structure

`ListCashDrawerShiftEventsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cursor` | `?string` | Optional | Opaque cursor for fetching the next page. Cursor is not present in<br>the last page of results. | getCursor(): ?string | setCursor(?string cursor): void |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `events` | [`?(CashDrawerShiftEvent[])`](../../doc/models/cash-drawer-shift-event.md) | Optional | All of the events (payments, refunds, etc.) for a cash drawer during<br>the shift. | getEvents(): ?array | setEvents(?array events): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\ListCashDrawerShiftEventsResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\CashDrawerShiftEventBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;

$listCashDrawerShiftEventsResponse = ListCashDrawerShiftEventsResponseBuilder::init()
    ->cursor('cursor2')
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
    ->events(
        [
            CashDrawerShiftEventBuilder::init()
                ->createdAt('2019-11-22T00:43:02.000Z')
                ->description('')
                ->employeeId('employee_id0')
                ->eventMoney(
                    MoneyBuilder::init()
                        ->amount(100)
                        ->currency('USD')
                        ->build()
                )
                ->eventType('CASH_TENDER_PAYMENT')
                ->id('9F07DB01-D85A-4B77-88C3-D5C64CEB5155')
                ->build(),
            CashDrawerShiftEventBuilder::init()
                ->createdAt('2019-11-22T00:43:12.000Z')
                ->description('')
                ->employeeId('employee_id0')
                ->eventMoney(
                    MoneyBuilder::init()
                        ->amount(250)
                        ->currency('USD')
                        ->build()
                )
                ->eventType('CASH_TENDER_PAYMENT')
                ->id('B2854CEA-A781-49B3-8F31-C64558231F48')
                ->build(),
            CashDrawerShiftEventBuilder::init()
                ->createdAt('2019-11-22T00:43:23.000Z')
                ->description('')
                ->employeeId('employee_id0')
                ->eventMoney(
                    MoneyBuilder::init()
                        ->amount(250)
                        ->currency('USD')
                        ->build()
                )
                ->eventType('CASH_TENDER_CANCELLED_PAYMENT')
                ->id('B5FB7F72-95CD-44A3-974D-26C41064D042')
                ->build(),
            CashDrawerShiftEventBuilder::init()
                ->createdAt('2019-11-22T00:43:46.000Z')
                ->description('')
                ->employeeId('employee_id0')
                ->eventMoney(
                    MoneyBuilder::init()
                        ->amount(100)
                        ->currency('USD')
                        ->build()
                )
                ->eventType('CASH_TENDER_REFUND')
                ->id('0B425480-8504-40B4-A867-37B23543931B')
                ->build(),
            CashDrawerShiftEventBuilder::init()
                ->createdAt('2019-11-22T00:44:18.000Z')
                ->description('Transfer from another drawer')
                ->employeeId('employee_id0')
                ->eventMoney(
                    MoneyBuilder::init()
                        ->amount(10000)
                        ->currency('USD')
                        ->build()
                )
                ->eventType('PAID_IN')
                ->id('8C66E60E-FDCF-4EEF-A98D-3B14B7ED5CBE')
                ->build(),
            CashDrawerShiftEventBuilder::init()
                ->createdAt('2019-11-22T00:44:29.000Z')
                ->description('Transfer out to another drawer')
                ->employeeId('employee_id0')
                ->eventMoney(
                    MoneyBuilder::init()
                        ->amount(10000)
                        ->currency('USD')
                        ->build()
                )
                ->eventType('PAID_OUT')
                ->id('D5ACA7FE-C64D-4ADA-8BC8-82118A2DAE4F')
                ->build()
        ]
    )
    ->build();
```

