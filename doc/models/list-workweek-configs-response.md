
# List Workweek Configs Response

The response to a request for a set of `WorkweekConfig` objects. The response contains
the requested `WorkweekConfig` objects and might contain a set of `Error` objects if
the request resulted in errors.

## Structure

`ListWorkweekConfigsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cursor` | `?string` | Optional | The value supplied in the subsequent request to fetch the next page of<br>`EmployeeWage` results. | getCursor(): ?string | setCursor(?string cursor): void |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `workweekConfigs` | [`?(WorkweekConfig[])`](../../doc/models/workweek-config.md) | Optional | A page of `EmployeeWage` results. | getWorkweekConfigs(): ?array | setWorkweekConfigs(?array workweekConfigs): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\ListWorkweekConfigsResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\WorkweekConfigBuilder;

$listWorkweekConfigsResponse = ListWorkweekConfigsResponseBuilder::init()
    ->cursor('2fofTniCgT0yIPAq26kmk0YyFQJZfbWkh73OOnlTHmTAx13NgED')
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
                ->build()
        ]
    )
    ->workweekConfigs(
        [
            WorkweekConfigBuilder::init(
                '10:00',
                'MON'
            )
                ->createdAt('2016-02-04T00:58:24Z')
                ->id('FY4VCAQN700GM')
                ->updatedAt('2019-02-28T01:04:35Z')
                ->version(11)
                ->build()
        ]
    )
    ->build();
```

