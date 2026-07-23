
# Update Team Member Request

Represents an update request for a `TeamMember` object.

## Structure

`UpdateTeamMemberRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `teamMember` | [`?TeamMember`](../../doc/models/team-member.md) | Optional | A record representing an individual team member for a business. | getTeamMember(): ?TeamMember | setTeamMember(?TeamMember teamMember): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\UpdateTeamMemberRequestBuilder;
use SquareConnectAPILib\Models\Builders\TeamMemberBuilder;
use SquareConnectAPILib\Models\Builders\TeamMemberAssignedLocationsBuilder;

$updateTeamMemberRequest = UpdateTeamMemberRequestBuilder::init()
    ->teamMember(
        TeamMemberBuilder::init()
            ->assignedLocations(
                TeamMemberAssignedLocationsBuilder::init()
                    ->assignmentType('assignment_type8')
                    ->locationIds(
                        [
                            'location_ids8',
                            'location_ids9',
                            'location_ids0'
                        ]
                    )
                    ->build()
            )
            ->createdAt('created_at4')
            ->emailAddress('email_address4')
            ->familyName('family_name0')
            ->givenName('given_name8')
            ->build()
    )
    ->build();
```

