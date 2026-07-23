
# Get Shift Response

A response to a request to get a `Shift`. The response contains
the requested `Shift` object and might contain a set of `Error` objects if
the request resulted in errors.

## Structure

`GetShiftResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `shift` | [`?Shift`](../../doc/models/shift.md) | Optional | A record of the hourly rate, start, and end times for a single work shift<br>for an employee. This might include a record of the start and end times for breaks<br>taken during the shift. | getShift(): ?Shift | setShift(?Shift shift): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\GetShiftResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\ShiftBuilder;
use SquareConnectAPILib\Models\Builders\MBreakBuilder;
use SquareConnectAPILib\Models\Builders\ShiftWageBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;

$getShiftResponse = GetShiftResponseBuilder::init()
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
    ->shift(
        ShiftBuilder::init(
            '2019-02-23T18:00:00-05:00'
        )
            ->breaks(
                [
                    MBreakBuilder::init(
                        '92EPDRQKJ5088',
                        'PT1H',
                        true,
                        'Lunch Break',
                        '2019-02-23T19:00:00-05:00'
                    )
                        ->endAt('2019-02-23T20:00:00-05:00')
                        ->id('M9BBKEPQAQD2T')
                        ->build()
                ]
            )
            ->createdAt('2019-02-27T00:12:12Z')
            ->employeeId('D71KRMQof6cXGUW0aAv7')
            ->endAt('2019-02-23T21:00:00-05:00')
            ->id('T35HMQSN89SV4')
            ->locationId('PAA1RJZZKXBFG')
            ->status('CLOSED')
            ->teamMemberId('D71KRMQof6cXGUW0aAv7')
            ->timezone('America/New_York')
            ->updatedAt('2019-02-27T00:12:12Z')
            ->version(1)
            ->wage(
                ShiftWageBuilder::init()
                    ->hourlyRate(
                        MoneyBuilder::init()
                            ->amount(1457)
                            ->currency('USD')
                            ->build()
                    )
                    ->title('Cashier')
                    ->build()
            )
            ->build()
    )
    ->build();
```

