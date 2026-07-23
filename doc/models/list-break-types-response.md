
# List Break Types Response

The response to a request for a set of `BreakType` objects. The response contains
the requested `BreakType` objects and might contain a set of `Error` objects if
the request resulted in errors.

## Structure

`ListBreakTypesResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `breakTypes` | [`?(BreakType[])`](../../doc/models/break-type.md) | Optional | A page of `BreakType` results. | getBreakTypes(): ?array | setBreakTypes(?array breakTypes): void |
| `cursor` | `?string` | Optional | The value supplied in the subsequent request to fetch the next page<br>of `BreakType` results. | getCursor(): ?string | setCursor(?string cursor): void |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\ListBreakTypesResponseBuilder;
use SquareConnectAPILib\Models\Builders\BreakTypeBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;

$listBreakTypesResponse = ListBreakTypesResponseBuilder::init()
    ->breakTypes(
        [
            BreakTypeBuilder::init(
                'Coffee Break',
                'PT5M',
                false,
                'PAA1RJZZKXBFG'
            )
                ->createdAt('2019-01-22T20:47:37Z')
                ->id('REGS1EQR1TPZ5')
                ->updatedAt('2019-01-22T20:47:37Z')
                ->version(1)
                ->build(),
            BreakTypeBuilder::init(
                'Lunch Break',
                'PT1H',
                true,
                'PAA1RJZZKXBFG'
            )
                ->createdAt('2019-01-25T19:26:30Z')
                ->id('92EPDRQKJ5088')
                ->updatedAt('2019-01-25T19:26:30Z')
                ->version(3)
                ->build()
        ]
    )
    ->cursor('2fofTniCgT0yIPAq26kmk0YyFQJZfbWkh73OOnlTHmTAx13NgED')
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
    ->build();
```

