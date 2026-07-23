
# List Team Member Wages Response

The response to a request for a set of `TeamMemberWage` objects. The response contains
a set of `TeamMemberWage` objects.

## Structure

`ListTeamMemberWagesResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cursor` | `?string` | Optional | The value supplied in the subsequent request to fetch the next page<br>of `TeamMemberWage` results. | getCursor(): ?string | setCursor(?string cursor): void |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `teamMemberWages` | [`?(TeamMemberWage[])`](../../doc/models/team-member-wage.md) | Optional | A page of `TeamMemberWage` results. | getTeamMemberWages(): ?array | setTeamMemberWages(?array teamMemberWages): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\ListTeamMemberWagesResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\TeamMemberWageBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;

$listTeamMemberWagesResponse = ListTeamMemberWagesResponseBuilder::init()
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
    ->teamMemberWages(
        [
            TeamMemberWageBuilder::init()
                ->hourlyRate(
                    MoneyBuilder::init()
                        ->amount(3250)
                        ->currency('USD')
                        ->build()
                )
                ->id('pXS3qCv7BERPnEGedM4S8mhm')
                ->teamMemberId('33fJchumvVdJwxV0H6L9')
                ->title('Manager')
                ->build(),
            TeamMemberWageBuilder::init()
                ->hourlyRate(
                    MoneyBuilder::init()
                        ->amount(2600)
                        ->currency('USD')
                        ->build()
                )
                ->id('rZduCkzYDUVL3ovh1sQgbue6')
                ->teamMemberId('33fJchumvVdJwxV0H6L9')
                ->title('Cook')
                ->build(),
            TeamMemberWageBuilder::init()
                ->hourlyRate(
                    MoneyBuilder::init()
                        ->amount(1600)
                        ->currency('USD')
                        ->build()
                )
                ->id('FxLbs5KpPUHa8wyt5ctjubDX')
                ->teamMemberId('33fJchumvVdJwxV0H6L9')
                ->title('Barista')
                ->build(),
            TeamMemberWageBuilder::init()
                ->hourlyRate(
                    MoneyBuilder::init()
                        ->amount(1700)
                        ->currency('USD')
                        ->build()
                )
                ->id('vD1wCgijMDR3cX5TPnu7VXto')
                ->teamMemberId('33fJchumvVdJwxV0H6L9')
                ->title('Cashier')
                ->build()
        ]
    )
    ->build();
```

