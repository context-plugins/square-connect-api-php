
# M Break

A record of an employee's break during a shift.

## Structure

`MBreak`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `breakTypeId` | `string` | Required | The `BreakType` that this `Break` was templated on.<br><br>**Constraints**: *Minimum Length*: `1` | getBreakTypeId(): string | setBreakTypeId(string breakTypeId): void |
| `endAt` | `?string` | Optional | RFC 3339; follows the same timezone information as `Shift`. Precision up to<br>the minute is respected; seconds are truncated. | getEndAt(): ?string | setEndAt(?string endAt): void |
| `expectedDuration` | `string` | Required | Format: RFC-3339 P[n]Y[n]M[n]DT[n]H[n]M[n]S. The expected length of<br>the break.<br><br>**Constraints**: *Minimum Length*: `1` | getExpectedDuration(): string | setExpectedDuration(string expectedDuration): void |
| `id` | `?string` | Optional | The UUID for this object. | getId(): ?string | setId(?string id): void |
| `isPaid` | `bool` | Required | Whether this break counts towards time worked for compensation<br>purposes. | getIsPaid(): bool | setIsPaid(bool isPaid): void |
| `name` | `string` | Required | A human-readable name.<br><br>**Constraints**: *Minimum Length*: `1` | getName(): string | setName(string name): void |
| `startAt` | `string` | Required | RFC 3339; follows the same timezone information as `Shift`. Precision up to<br>the minute is respected; seconds are truncated.<br><br>**Constraints**: *Minimum Length*: `1` | getStartAt(): string | setStartAt(string startAt): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\MBreakBuilder;

$break = MBreakBuilder::init(
    'break_type_id2',
    'expected_duration8',
    false,
    'name6',
    'start_at8'
)
    ->endAt('end_at4')
    ->id('id6')
    ->build();
```

