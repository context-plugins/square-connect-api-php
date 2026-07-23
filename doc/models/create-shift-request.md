
# Create Shift Request

Represents a request to create a `Shift`.

## Structure

`CreateShiftRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `idempotencyKey` | `?string` | Optional | A unique string value to ensure the idempotency of the operation.<br><br>**Constraints**: *Maximum Length*: `128` | getIdempotencyKey(): ?string | setIdempotencyKey(?string idempotencyKey): void |
| `shift` | [`Shift`](../../doc/models/shift.md) | Required | A record of the hourly rate, start, and end times for a single work shift<br>for an employee. This might include a record of the start and end times for breaks<br>taken during the shift. | getShift(): Shift | setShift(Shift shift): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CreateShiftRequestBuilder;
use SquareConnectAPILib\Models\Builders\ShiftBuilder;
use SquareConnectAPILib\Models\Builders\MBreakBuilder;

$createShiftRequest = CreateShiftRequestBuilder::init(
    ShiftBuilder::init(
        'start_at6'
    )
        ->breaks(
            [
                MBreakBuilder::init(
                    'break_type_id2',
                    'expected_duration8',
                    false,
                    'name6',
                    'start_at8'
                )
                    ->endAt('end_at4')
                    ->id('id6')
                    ->build(),
                MBreakBuilder::init(
                    'break_type_id2',
                    'expected_duration8',
                    false,
                    'name6',
                    'start_at8'
                )
                    ->endAt('end_at4')
                    ->id('id6')
                    ->build(),
                MBreakBuilder::init(
                    'break_type_id2',
                    'expected_duration8',
                    false,
                    'name6',
                    'start_at8'
                )
                    ->endAt('end_at4')
                    ->id('id6')
                    ->build()
            ]
        )
        ->createdAt('created_at2')
        ->employeeId('employee_id4')
        ->endAt('end_at6')
        ->id('id4')
        ->build()
)
    ->idempotencyKey('idempotency_key0')
    ->build();
```

