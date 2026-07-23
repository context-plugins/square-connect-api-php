
# Team Member Wage

The hourly wage rate that a team member earns on a `Shift` for doing the job
specified by the `title` property of this object.

## Structure

`TeamMemberWage`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `hourlyRate` | [`?Money`](../../doc/models/money.md) | Optional | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getHourlyRate(): ?Money | setHourlyRate(?Money hourlyRate): void |
| `id` | `?string` | Optional | The UUID for this object. | getId(): ?string | setId(?string id): void |
| `teamMemberId` | `?string` | Optional | The `TeamMember` that this wage is assigned to. | getTeamMemberId(): ?string | setTeamMemberId(?string teamMemberId): void |
| `title` | `?string` | Optional | The job title that this wage relates to. | getTitle(): ?string | setTitle(?string title): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\TeamMemberWageBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;

$teamMemberWage = TeamMemberWageBuilder::init()
    ->hourlyRate(
        MoneyBuilder::init()
            ->amount(172)
            ->currency('currency0')
            ->build()
    )
    ->id('id8')
    ->teamMemberId('team_member_id2')
    ->title('title6')
    ->build();
```

