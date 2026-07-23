
# Get Team Member Wage Response

A response to a request to get a `TeamMemberWage`. The response contains
the requested `TeamMemberWage` objects and might contain a set of `Error` objects if
the request resulted in errors.

## Structure

`GetTeamMemberWageResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `teamMemberWage` | [`?TeamMemberWage`](../../doc/models/team-member-wage.md) | Optional | The hourly wage rate that a team member earns on a `Shift` for doing the job<br>specified by the `title` property of this object. | getTeamMemberWage(): ?TeamMemberWage | setTeamMemberWage(?TeamMemberWage teamMemberWage): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\GetTeamMemberWageResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\TeamMemberWageBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;

$getTeamMemberWageResponse = GetTeamMemberWageResponseBuilder::init()
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
    ->teamMemberWage(
        TeamMemberWageBuilder::init()
            ->hourlyRate(
                MoneyBuilder::init()
                    ->amount(2000)
                    ->currency('USD')
                    ->build()
            )
            ->id('pXS3qCv7BERPnEGedM4S8mhm')
            ->teamMemberId('33fJchumvVdJwxV0H6L9')
            ->title('Manager')
            ->build()
    )
    ->build();
```

