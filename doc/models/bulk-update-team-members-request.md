
# Bulk Update Team Members Request

Represents a bulk update request for `TeamMember` objects.

## Structure

`BulkUpdateTeamMembersRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `teamMembers` | [`array<string,UpdateTeamMemberRequest>`](../../doc/models/update-team-member-request.md) | Required | The data used to update the `TeamMember` objects. Each key is the `team_member_id` that maps to the `UpdateTeamMemberRequest`. | getTeamMembers(): array | setTeamMembers(array teamMembers): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\BulkUpdateTeamMembersRequestBuilder;
use SquareConnectAPILib\Models\Builders\UpdateTeamMemberRequestBuilder;
use SquareConnectAPILib\Models\Builders\TeamMemberBuilder;
use SquareConnectAPILib\Models\Builders\TeamMemberAssignedLocationsBuilder;

$bulkUpdateTeamMembersRequest = BulkUpdateTeamMembersRequestBuilder::init(
    [
        'key0' => UpdateTeamMemberRequestBuilder::init()
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
            ->build()
    ]
)->build();
```

