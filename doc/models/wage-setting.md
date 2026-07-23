
# Wage Setting

An object representing a team member's wage information.

## Structure

`WageSetting`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `createdAt` | `?string` | Optional | The timestamp, in RFC 3339 format, describing when the wage setting object was created.<br>For example, "2018-10-04T04:00:00-07:00" or "2019-02-05T12:00:00Z". | getCreatedAt(): ?string | setCreatedAt(?string createdAt): void |
| `isOvertimeExempt` | `?bool` | Optional | Whether the team member is exempt from the overtime rules of the seller's country. | getIsOvertimeExempt(): ?bool | setIsOvertimeExempt(?bool isOvertimeExempt): void |
| `jobAssignments` | [`?(JobAssignment[])`](../../doc/models/job-assignment.md) | Optional | Required. The ordered list of jobs that the team member is assigned to.<br>The first job assignment is considered the team member's primary job.<br><br>The minimum length is 1 and the maximum length is 12. | getJobAssignments(): ?array | setJobAssignments(?array jobAssignments): void |
| `teamMemberId` | `?string` | Optional | The unique ID of the `TeamMember` whom this wage setting describes. | getTeamMemberId(): ?string | setTeamMemberId(?string teamMemberId): void |
| `updatedAt` | `?string` | Optional | The timestamp, in RFC 3339 format, describing when the wage setting object was last updated.<br>For example, "2018-10-04T04:00:00-07:00" or "2019-02-05T12:00:00Z". | getUpdatedAt(): ?string | setUpdatedAt(?string updatedAt): void |
| `version` | `?int` | Optional | Used for resolving concurrency issues. The request fails if the version<br>provided does not match the server version at the time of the request. If not provided,<br>Square executes a blind write, potentially overwriting data from another write. For more information,<br>see [optimistic concurrency](https://developer.squareup.com/docs/working-with-apis/optimistic-concurrency). | getVersion(): ?int | setVersion(?int version): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\WageSettingBuilder;
use SquareConnectAPILib\Models\Builders\JobAssignmentBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;

$wageSetting = WageSettingBuilder::init()
    ->createdAt('created_at0')
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
    ->teamMemberId('team_member_id2')
    ->updatedAt('updated_at8')
    ->build();
```

