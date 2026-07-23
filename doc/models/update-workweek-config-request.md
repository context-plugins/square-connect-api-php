
# Update Workweek Config Request

A request to update a `WorkweekConfig` object.

## Structure

`UpdateWorkweekConfigRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `workweekConfig` | [`WorkweekConfig`](../../doc/models/workweek-config.md) | Required | Sets the day of the week and hour of the day that a business starts a<br>workweek. This is used to calculate overtime pay. | getWorkweekConfig(): WorkweekConfig | setWorkweekConfig(WorkweekConfig workweekConfig): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\UpdateWorkweekConfigRequestBuilder;
use SquareConnectAPILib\Models\Builders\WorkweekConfigBuilder;

$updateWorkweekConfigRequest = UpdateWorkweekConfigRequestBuilder::init(
    WorkweekConfigBuilder::init(
        'start_of_day_local_time6',
        'start_of_week2'
    )
        ->createdAt('created_at8')
        ->id('id0')
        ->updatedAt('updated_at6')
        ->version(42)
        ->build()
)->build();
```

