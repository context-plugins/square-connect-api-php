
# Create Break Type Request

A request to create a new `BreakType`.

## Structure

`CreateBreakTypeRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `breakType` | [`BreakType`](../../doc/models/break-type.md) | Required | A defined break template that sets an expectation for possible `Break`<br>instances on a `Shift`. | getBreakType(): BreakType | setBreakType(BreakType breakType): void |
| `idempotencyKey` | `?string` | Optional | A unique string value to ensure the idempotency of the operation.<br><br>**Constraints**: *Maximum Length*: `128` | getIdempotencyKey(): ?string | setIdempotencyKey(?string idempotencyKey): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CreateBreakTypeRequestBuilder;
use SquareConnectAPILib\Models\Builders\BreakTypeBuilder;

$createBreakTypeRequest = CreateBreakTypeRequestBuilder::init(
    BreakTypeBuilder::init(
        'break_name0',
        'expected_duration6',
        false,
        'location_id2'
    )
        ->createdAt('created_at6')
        ->id('id8')
        ->updatedAt('updated_at4')
        ->version(132)
        ->build()
)
    ->idempotencyKey('idempotency_key4')
    ->build();
```

