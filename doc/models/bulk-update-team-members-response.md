
# Bulk Update Team Members Response

Represents a response from a bulk update request containing the updated `TeamMember` objects or error messages.

## Structure

`BulkUpdateTeamMembersResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | The errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `teamMembers` | [`?array<string,UpdateTeamMemberResponse>`](../../doc/models/update-team-member-response.md) | Optional | The successfully updated `TeamMember` objects. Each key is the `team_member_id` that maps to the `UpdateTeamMemberRequest`. | getTeamMembers(): ?array | setTeamMembers(?array teamMembers): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\BulkUpdateTeamMembersResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\UpdateTeamMemberResponseBuilder;
use SquareConnectAPILib\Models\Builders\TeamMemberBuilder;
use SquareConnectAPILib\Models\Builders\TeamMemberAssignedLocationsBuilder;

$bulkUpdateTeamMembersResponse = BulkUpdateTeamMembersResponseBuilder::init()
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
    ->teamMembers(
        [
            'AFMwA08kR-MIF-3Vs0OE' => UpdateTeamMemberResponseBuilder::init()
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
                            ->build()
                    ]
                )
                ->teamMember(
                    TeamMemberBuilder::init()
                        ->assignedLocations(
                            TeamMemberAssignedLocationsBuilder::init()
                                ->assignmentType('ALL_CURRENT_AND_FUTURE_LOCATIONS')
                                ->locationIds(
                                    [
                                        'location_ids8',
                                        'location_ids9',
                                        'location_ids0'
                                    ]
                                )
                                ->build()
                        )
                        ->createdAt('2020-06-11T22:46:57.001Z')
                        ->emailAddress('jane_smith@gmail.com')
                        ->familyName('Smith')
                        ->givenName('Jane')
                        ->id('AFMwA08kR-MIF-3Vs0OE')
                        ->isOwner(false)
                        ->phoneNumber('+14159223334')
                        ->referenceId('reference_id_2')
                        ->status('ACTIVE')
                        ->build()
                )
                ->build(),
            'fpgteZNMaf0qOK-a4t6P' => UpdateTeamMemberResponseBuilder::init()
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
                        ->createdAt('2020-06-11T22:46:57.095Z')
                        ->emailAddress('joe_doe@gmail.com')
                        ->familyName('Doe')
                        ->givenName('Joe')
                        ->id('fpgteZNMaf0qOK-a4t6P')
                        ->isOwner(false)
                        ->phoneNumber('+14159283333')
                        ->referenceId('reference_id_1')
                        ->status('ACTIVE')
                        ->build()
                )
                ->build()
        ]
    )
    ->build();
```

