
# Update Wage Setting Request

Represents an update request for the `WageSetting` object describing a `TeamMember`.

## Structure

`UpdateWageSettingRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `wageSetting` | [`WageSetting`](../../doc/models/wage-setting.md) | Required | An object representing a team member's wage information. | getWageSetting(): WageSetting | setWageSetting(WageSetting wageSetting): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\UpdateWageSettingRequestBuilder;
use SquareConnectAPILib\Models\Builders\WageSettingBuilder;
use SquareConnectAPILib\Models\Builders\JobAssignmentBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;

$updateWageSettingRequest = UpdateWageSettingRequestBuilder::init(
    WageSettingBuilder::init()
        ->createdAt('created_at6')
        ->isOvertimeExempt(false)
        ->jobAssignments(
            [
                JobAssignmentBuilder::init(
                    'job_title6',
                    'pay_type2'
                )
                    ->annualRate(
                        MoneyBuilder::init()
                            ->amount(232)
                            ->currency('currency2')
                            ->build()
                    )
                    ->hourlyRate(
                        MoneyBuilder::init()
                            ->amount(172)
                            ->currency('currency0')
                            ->build()
                    )
                    ->weeklyHours(98)
                    ->build(),
                JobAssignmentBuilder::init(
                    'job_title6',
                    'pay_type2'
                )
                    ->annualRate(
                        MoneyBuilder::init()
                            ->amount(232)
                            ->currency('currency2')
                            ->build()
                    )
                    ->hourlyRate(
                        MoneyBuilder::init()
                            ->amount(172)
                            ->currency('currency0')
                            ->build()
                    )
                    ->weeklyHours(98)
                    ->build()
            ]
        )
        ->teamMemberId('team_member_id8')
        ->updatedAt('updated_at4')
        ->build()
)->build();
```

