
# Update Workweek Config Response

The response to a request to update a `WorkweekConfig` object. The response contains
the updated `WorkweekConfig` object and might contain a set of `Error` objects if
the request resulted in errors.

## Structure

`UpdateWorkweekConfigResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `workweekConfig` | [`?WorkweekConfig`](../../doc/models/workweek-config.md) | Optional | Sets the day of the week and hour of the day that a business starts a<br>workweek. This is used to calculate overtime pay. | getWorkweekConfig(): ?WorkweekConfig | setWorkweekConfig(?WorkweekConfig workweekConfig): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\UpdateWorkweekConfigResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\WorkweekConfigBuilder;

$updateWorkweekConfigResponse = UpdateWorkweekConfigResponseBuilder::init()
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
    ->workweekConfig(
        WorkweekConfigBuilder::init(
            '10:00',
            'MON'
        )
            ->createdAt('2016-02-04T00:58:24Z')
            ->id('FY4VCAQN700GM')
            ->updatedAt('2019-02-28T01:04:35Z')
            ->version(11)
            ->build()
    )
    ->build();
```

