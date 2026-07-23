
# Search Shifts Response

The response to a request for `Shift` objects. The response contains
the requested `Shift` objects and might contain a set of `Error` objects if
the request resulted in errors.

## Structure

`SearchShiftsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cursor` | `?string` | Optional | An opaque cursor for fetching the next page. | getCursor(): ?string | setCursor(?string cursor): void |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `shifts` | [`?(Shift[])`](../../doc/models/shift.md) | Optional | Shifts. | getShifts(): ?array | setShifts(?array shifts): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\SearchShiftsResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\ShiftBuilder;
use SquareConnectAPILib\Models\Builders\MBreakBuilder;
use SquareConnectAPILib\Models\Builders\ShiftWageBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;

$searchShiftsResponse = SearchShiftsResponseBuilder::init()
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
    ->shifts(
        [
            ShiftBuilder::init(
                '2019-01-21T03:11:00-05:00'
            )
                ->breaks(
                    [
                        MBreakBuilder::init(
                            'REGS1EQR1TPZ5',
                            'PT10M',
                            true,
                            'Tea Break',
                            '2019-01-21T06:11:00-05:00'
                        )
                            ->endAt('2019-01-21T06:11:00-05:00')
                            ->id('SJW7X6AKEJQ65')
                            ->build()
                    ]
                )
                ->createdAt('2019-01-24T01:12:03Z')
                ->employeeId('ormj0jJJZ5OZIzxrZYJI')
                ->endAt('2019-01-21T13:11:00-05:00')
                ->id('X714F3HA6D1PT')
                ->locationId('PAA1RJZZKXBFG')
                ->status('CLOSED')
                ->teamMemberId('ormj0jJJZ5OZIzxrZYJI')
                ->timezone('America/New_York')
                ->updatedAt('2019-02-07T22:21:08Z')
                ->version(6)
                ->wage(
                    ShiftWageBuilder::init()
                        ->hourlyRate(
                            MoneyBuilder::init()
                                ->amount(1100)
                                ->currency('USD')
                                ->build()
                        )
                        ->title('Barista')
                        ->build()
                )
                ->build(),
            ShiftBuilder::init(
                '2019-01-22T12:02:00-05:00'
            )
                ->breaks(
                    [
                        MBreakBuilder::init(
                            'WQX00VR99F53J',
                            'PT10M',
                            true,
                            'Tea Break',
                            '2019-01-23T14:30:00-05:00'
                        )
                            ->endAt('2019-01-23T14:40:00-05:00')
                            ->id('BKS6VR7WR748A')
                            ->build(),
                        MBreakBuilder::init(
                            'P6Q468ZFRN1AC',
                            'PT15M',
                            false,
                            'Coffee Break',
                            '2019-01-22T12:30:00-05:00'
                        )
                            ->endAt('2019-01-22T12:44:00-05:00')
                            ->id('BQFEZSHFZSC51')
                            ->build()
                    ]
                )
                ->createdAt('2019-01-23T23:32:45Z')
                ->employeeId('33fJchumvVdJwxV0H6L9')
                ->endAt('2019-01-22T13:02:00-05:00')
                ->id('GDHYBZYWK0P2V')
                ->locationId('PAA1RJZZKXBFG')
                ->status('CLOSED')
                ->teamMemberId('33fJchumvVdJwxV0H6L9')
                ->timezone('America/New_York')
                ->updatedAt('2019-01-24T00:56:25Z')
                ->version(16)
                ->wage(
                    ShiftWageBuilder::init()
                        ->hourlyRate(
                            MoneyBuilder::init()
                                ->amount(1600)
                                ->currency('USD')
                                ->build()
                        )
                        ->title('Cook')
                        ->build()
                )
                ->build()
        ]
    )
    ->build();
```

