
# Update Shift Response

The response to a request to update a `Shift`. The response contains
the updated `Shift` object and might contain a set of `Error` objects if
the request resulted in errors.

## Structure

`UpdateShiftResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `shift` | [`?Shift`](../../doc/models/shift.md) | Optional | A record of the hourly rate, start, and end times for a single work shift<br>for an employee. This might include a record of the start and end times for breaks<br>taken during the shift. | getShift(): ?Shift | setShift(?Shift shift): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\UpdateShiftResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\ShiftBuilder;
use SquareConnectAPILib\Models\Builders\MBreakBuilder;
use SquareConnectAPILib\Models\Builders\ShiftWageBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;

$updateShiftResponse = UpdateShiftResponseBuilder::init()
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
    ->shift(
        ShiftBuilder::init(
            '2019-01-25T03:11:00-05:00'
        )
            ->breaks(
                [
                    MBreakBuilder::init(
                        'REGS1EQR1TPZ5',
                        'PT5M',
                        true,
                        'Tea Break',
                        '2019-01-25T06:11:00-05:00'
                    )
                        ->endAt('2019-01-25T06:16:00-05:00')
                        ->id('X7GAQYVVRRG6P')
                        ->build()
                ]
            )
            ->createdAt('2019-02-28T00:39:02Z')
            ->employeeId('ormj0jJJZ5OZIzxrZYJI')
            ->endAt('2019-01-25T13:11:00-05:00')
            ->id('K0YH4CV5462JB')
            ->locationId('PAA1RJZZKXBFG')
            ->status('CLOSED')
            ->teamMemberId('ormj0jJJZ5OZIzxrZYJI')
            ->timezone('America/New_York')
            ->updatedAt('2019-02-28T00:42:41Z')
            ->version(2)
            ->wage(
                ShiftWageBuilder::init()
                    ->hourlyRate(
                        MoneyBuilder::init()
                            ->amount(1500)
                            ->currency('USD')
                            ->build()
                    )
                    ->title('Bartender')
                    ->build()
            )
            ->build()
    )
    ->build();
```

