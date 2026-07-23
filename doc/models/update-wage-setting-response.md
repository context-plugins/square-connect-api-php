
# Update Wage Setting Response

Represents a response from an update request containing the updated `WageSetting` object
or error messages.

## Structure

`UpdateWageSettingResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | The errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `wageSetting` | [`?WageSetting`](../../doc/models/wage-setting.md) | Optional | An object representing a team member's wage information. | getWageSetting(): ?WageSetting | setWageSetting(?WageSetting wageSetting): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\UpdateWageSettingResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\WageSettingBuilder;
use SquareConnectAPILib\Models\Builders\JobAssignmentBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;

$updateWageSettingResponse = UpdateWageSettingResponseBuilder::init()
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
    ->wageSetting(
        WageSettingBuilder::init()
            ->createdAt('2019-07-10T17:26:48+00:00')
            ->isOvertimeExempt(true)
            ->jobAssignments(
                [
                    JobAssignmentBuilder::init(
                        'Manager',
                        'SALARY'
                    )
                        ->annualRate(
                            MoneyBuilder::init()
                                ->amount(3000000)
                                ->currency('USD')
                                ->build()
                        )
                        ->hourlyRate(
                            MoneyBuilder::init()
                                ->amount(1443)
                                ->currency('USD')
                                ->build()
                        )
                        ->weeklyHours(40)
                        ->build(),
                    JobAssignmentBuilder::init(
                        'Cashier',
                        'HOURLY'
                    )
                        ->annualRate(
                            MoneyBuilder::init()
                                ->amount(232)
                                ->currency('currency2')
                                ->build()
                        )
                        ->hourlyRate(
                            MoneyBuilder::init()
                                ->amount(1200)
                                ->currency('USD')
                                ->build()
                        )
                        ->weeklyHours(98)
                        ->build()
                ]
            )
            ->teamMemberId('-3oZQKPKVk6gUXU_V5Qa')
            ->updatedAt('2020-06-11T23:12:04+00:00')
            ->version(1)
            ->build()
    )
    ->build();
```

