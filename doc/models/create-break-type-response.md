
# Create Break Type Response

The response to the request to create a `BreakType`. The response contains
the created `BreakType` object and might contain a set of `Error` objects if
the request resulted in errors.

## Structure

`CreateBreakTypeResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `breakType` | [`?BreakType`](../../doc/models/break-type.md) | Optional | A defined break template that sets an expectation for possible `Break`<br>instances on a `Shift`. | getBreakType(): ?BreakType | setBreakType(?BreakType breakType): void |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CreateBreakTypeResponseBuilder;
use SquareConnectAPILib\Models\Builders\BreakTypeBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;

$createBreakTypeResponse = CreateBreakTypeResponseBuilder::init()
    ->breakType(
        BreakTypeBuilder::init(
            'Lunch Break',
            'PT30M',
            true,
            'CGJN03P1D08GF'
        )
            ->createdAt('2019-02-26T22:42:54Z')
            ->id('49SSVDJG76WF3')
            ->updatedAt('2019-02-26T22:42:54Z')
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

