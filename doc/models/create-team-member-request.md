
# Create Team Member Request

Represents a create request for a `TeamMember` object.

## Structure

`CreateTeamMemberRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `idempotencyKey` | `?string` | Optional | A unique string that identifies this `CreateTeamMember` request.<br>Keys can be any valid string, but must be unique for every request.<br>For more information, see [Idempotency](https://developer.squareup.com/docs/basics/api101/idempotency).<br><br>The minimum length is 1 and the maximum length is 45. | getIdempotencyKey(): ?string | setIdempotencyKey(?string idempotencyKey): void |
| `teamMember` | [`?TeamMember`](../../doc/models/team-member.md) | Optional | A record representing an individual team member for a business. | getTeamMember(): ?TeamMember | setTeamMember(?TeamMember teamMember): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CreateTeamMemberRequestBuilder;
use SquareConnectAPILib\Models\Builders\TeamMemberBuilder;
use SquareConnectAPILib\Models\Builders\TeamMemberAssignedLocationsBuilder;

$createTeamMemberRequest = CreateTeamMemberRequestBuilder::init()
    ->idempotencyKey('idempotency_key8')
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

