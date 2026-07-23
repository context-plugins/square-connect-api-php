
# Get Break Type Response

The response to a request to get a `BreakType`. The response contains
the requested `BreakType` objects and might contain a set of `Error` objects if
the request resulted in errors.

## Structure

`GetBreakTypeResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `breakType` | [`?BreakType`](../../doc/models/break-type.md) | Optional | A defined break template that sets an expectation for possible `Break`<br>instances on a `Shift`. | getBreakType(): ?BreakType | setBreakType(?BreakType breakType): void |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\GetBreakTypeResponseBuilder;
use SquareConnectAPILib\Models\Builders\BreakTypeBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;

$getBreakTypeResponse = GetBreakTypeResponseBuilder::init()
    ->breakType(
        BreakTypeBuilder::init(
            'Lunch Break',
            'PT30M',
            true,
            '059SB0E0WCNWS'
        )
            ->createdAt('2019-02-21T17:50:00Z')
            ->id('lA0mj_RSOprNPwMUXdYp')
            ->updatedAt('2019-02-21T17:50:00Z')
            ->version(1)
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

