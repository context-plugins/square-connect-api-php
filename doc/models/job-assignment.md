
# Job Assignment

An object describing a job that a team member is assigned to.

## Structure

`JobAssignment`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `annualRate` | [`?Money`](../../doc/models/money.md) | Optional | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getAnnualRate(): ?Money | setAnnualRate(?Money annualRate): void |
| `hourlyRate` | [`?Money`](../../doc/models/money.md) | Optional | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getHourlyRate(): ?Money | setHourlyRate(?Money hourlyRate): void |
| `jobTitle` | `string` | Required | The title of the job.<br><br>**Constraints**: *Minimum Length*: `1` | getJobTitle(): string | setJobTitle(string jobTitle): void |
| `payType` | `string` | Required | The current pay type for the job assignment used to<br>calculate the pay amount in a pay period. | getPayType(): string | setPayType(string payType): void |
| `weeklyHours` | `?int` | Optional | The planned hours per week for the job. Set if the job `PayType` is `SALARY`. | getWeeklyHours(): ?int | setWeeklyHours(?int weeklyHours): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\JobAssignmentBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;

$jobAssignment = JobAssignmentBuilder::init(
    'job_title0',
    'pay_type6'
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
    ->weeklyHours(190)
    ->build();
```

