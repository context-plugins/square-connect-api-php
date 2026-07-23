
# Bulk Create Team Members Response

Represents a response from a bulk create request containing the created `TeamMember` objects or error messages.

## Structure

`BulkCreateTeamMembersResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | The errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `teamMembers` | [`?array<string,CreateTeamMemberResponse>`](../../doc/models/create-team-member-response.md) | Optional | The successfully created `TeamMember` objects. Each key is the `idempotency_key` that maps to the `CreateTeamMemberRequest`. | getTeamMembers(): ?array | setTeamMembers(?array teamMembers): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\BulkCreateTeamMembersResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\CreateTeamMemberResponseBuilder;
use SquareConnectAPILib\Models\Builders\TeamMemberBuilder;
use SquareConnectAPILib\Models\Builders\TeamMemberAssignedLocationsBuilder;

$bulkCreateTeamMembersResponse = BulkCreateTeamMembersResponseBuilder::init()
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
    ->teamMembers(
        [
            'idempotency-key-1' => CreateTeamMemberResponseBuilder::init()
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
                        ->createdAt('created_at4')
                        ->emailAddress('joe_doe@gmail.com')
                        ->familyName('Doe')
                        ->givenName('Joe')
                        ->id('ywhG1qfIOoqsHfVRubFV')
                        ->isOwner(false)
                        ->phoneNumber('+14159283333')
                        ->referenceId('reference_id_1')
                        ->status('ACTIVE')
                        ->build()
                )
                ->build(),
            'idempotency-key-2' => CreateTeamMemberResponseBuilder::init()
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
                        ->createdAt('created_at4')
                        ->emailAddress('jane_smith@gmail.com')
                        ->familyName('Smith')
                        ->givenName('Jane')
                        ->id('IF_Ncrg7fHhCqxVI9T6R')
                        ->isOwner(false)
                        ->phoneNumber('+14159223334')
                        ->referenceId('reference_id_2')
                        ->status('ACTIVE')
                        ->build()
                )
                ->build()
        ]
    )
    ->build();
```

