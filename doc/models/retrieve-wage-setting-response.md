
# Retrieve Wage Setting Response

Represents a response from a retrieve request containing the specified `WageSetting` object or error messages.

## Structure

`RetrieveWageSettingResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | The errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `wageSetting` | [`?WageSetting`](../../doc/models/wage-setting.md) | Optional | An object representing a team member's wage information. | getWageSetting(): ?WageSetting | setWageSetting(?WageSetting wageSetting): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\RetrieveWageSettingResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\WageSettingBuilder;
use SquareConnectAPILib\Models\Builders\JobAssignmentBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;

$retrieveWageSettingResponse = RetrieveWageSettingResponseBuilder::init()
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
    ->wageSetting(
        WageSettingBuilder::init()
            ->createdAt('2020-06-11T23:01:21+00:00')
            ->isOvertimeExempt(false)
            ->jobAssignments(
                [
                    JobAssignmentBuilder::init(
                        'Manager',
                        'SALARY'
                    )
                        ->annualRate(
                            MoneyBuilder::init()
                                ->amount(4500000)
                                ->currency('USD')
                                ->build()
                        )
                        ->hourlyRate(
                            MoneyBuilder::init()
                                ->amount(2164)
                                ->currency('USD')
                                ->build()
                        )
                        ->weeklyHours(40)
                        ->build()
                ]
            )
            ->teamMemberId('1yJlHapkseYnNPETIU1B')
            ->updatedAt('2020-06-11T23:01:21+00:00')
            ->version(1)
            ->build()
    )
    ->build();
```

