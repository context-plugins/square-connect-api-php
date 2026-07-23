
# Create Team Member Response

Represents a response from a create request containing the created `TeamMember` object or error messages.

## Structure

`CreateTeamMemberResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | The errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `teamMember` | [`?TeamMember`](../../doc/models/team-member.md) | Optional | A record representing an individual team member for a business. | getTeamMember(): ?TeamMember | setTeamMember(?TeamMember teamMember): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CreateTeamMemberResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\TeamMemberBuilder;
use SquareConnectAPILib\Models\Builders\TeamMemberAssignedLocationsBuilder;

$createTeamMemberResponse = CreateTeamMemberResponseBuilder::init()
    ->errors(
        [
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
            ->createdAt('created_at4')
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

