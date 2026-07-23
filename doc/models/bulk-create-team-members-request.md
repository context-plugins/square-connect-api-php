
# Bulk Create Team Members Request

Represents a bulk create request for `TeamMember` objects.

## Structure

`BulkCreateTeamMembersRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `teamMembers` | [`array<string,CreateTeamMemberRequest>`](../../doc/models/create-team-member-request.md) | Required | The data used to create the `TeamMember` objects. Each key is the `idempotency_key` that maps to the `CreateTeamMemberRequest`. | getTeamMembers(): array | setTeamMembers(array teamMembers): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\BulkCreateTeamMembersRequestBuilder;
use SquareConnectAPILib\Models\Builders\CreateTeamMemberRequestBuilder;
use SquareConnectAPILib\Models\Builders\TeamMemberBuilder;
use SquareConnectAPILib\Models\Builders\TeamMemberAssignedLocationsBuilder;

$bulkCreateTeamMembersRequest = BulkCreateTeamMembersRequestBuilder::init(
    [
        'key0' => CreateTeamMemberRequestBuilder::init()
            ->idempotencyKey('idempotency_key4')
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
            ->build(),
        'key1' => CreateTeamMemberRequestBuilder::init()
            ->idempotencyKey('idempotency_key4')
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
            ->build(),
        'key2' => CreateTeamMemberRequestBuilder::init()
            ->idempotencyKey('idempotency_key4')
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

