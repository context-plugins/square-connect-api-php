
# Update Team Member Response

Represents a response from an update request containing the updated `TeamMember` object or error messages.

## Structure

`UpdateTeamMemberResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | The errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `teamMember` | [`?TeamMember`](../../doc/models/team-member.md) | Optional | A record representing an individual team member for a business. | getTeamMember(): ?TeamMember | setTeamMember(?TeamMember teamMember): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\UpdateTeamMemberResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\TeamMemberBuilder;
use SquareConnectAPILib\Models\Builders\TeamMemberAssignedLocationsBuilder;

$updateTeamMemberResponse = UpdateTeamMemberResponseBuilder::init()
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
    ->teamMember(
        TeamMemberBuilder::init()
            ->assignedLocations(
                TeamMemberAssignedLocationsBuilder::init()
                    ->assignmentType('EXPLICIT_LOCATIONS')
                    ->locationIds(
                        [
                            'GA2Y9HSJ8KRYT',
                            'YSGH2WBKG94QZ'
                        ]
                    )
                    ->build()
            )
            ->createdAt('2020-06-11T22:55:45.867Z')
            ->emailAddress('joe_doe@gmail.com')
            ->familyName('Doe')
            ->givenName('Joe')
            ->id('1yJlHapkseYnNPETIU1B')
            ->isOwner(false)
            ->phoneNumber('+14159283333')
            ->referenceId('reference_id_1')
            ->status('ACTIVE')
            ->build()
    )
    ->build();
```

