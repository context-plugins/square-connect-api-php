
# Update Break Type Request

A request to update a `BreakType`.

## Structure

`UpdateBreakTypeRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `breakType` | [`BreakType`](../../doc/models/break-type.md) | Required | A defined break template that sets an expectation for possible `Break`<br>instances on a `Shift`. | getBreakType(): BreakType | setBreakType(BreakType breakType): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\UpdateBreakTypeRequestBuilder;
use SquareConnectAPILib\Models\Builders\BreakTypeBuilder;

$updateBreakTypeRequest = UpdateBreakTypeRequestBuilder::init(
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
)->build();
```

