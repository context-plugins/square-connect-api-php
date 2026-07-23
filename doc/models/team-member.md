
# Team Member

A record representing an individual team member for a business.

## Structure

`TeamMember`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `assignedLocations` | [`?TeamMemberAssignedLocations`](../../doc/models/team-member-assigned-locations.md) | Optional | An object that represents a team member's assignment to locations. | getAssignedLocations(): ?TeamMemberAssignedLocations | setAssignedLocations(?TeamMemberAssignedLocations assignedLocations): void |
| `createdAt` | `?string` | Optional | The timestamp, in RFC 3339 format, describing when the team member was created.<br>For example, "2018-10-04T04:00:00-07:00" or "2019-02-05T12:00:00Z". | getCreatedAt(): ?string | setCreatedAt(?string createdAt): void |
| `emailAddress` | `?string` | Optional | The email address associated with the team member. | getEmailAddress(): ?string | setEmailAddress(?string emailAddress): void |
| `familyName` | `?string` | Optional | The family name (that is, the last name) associated with the team member. | getFamilyName(): ?string | setFamilyName(?string familyName): void |
| `givenName` | `?string` | Optional | The given name (that is, the first name) associated with the team member. | getGivenName(): ?string | setGivenName(?string givenName): void |
| `id` | `?string` | Optional | The unique ID for the team member. | getId(): ?string | setId(?string id): void |
| `isOwner` | `?bool` | Optional | Whether the team member is the owner of the Square account. | getIsOwner(): ?bool | setIsOwner(?bool isOwner): void |
| `phoneNumber` | `?string` | Optional | The team member's phone number, in E.164 format. For example:<br>+14155552671 - the country code is 1 for US<br>+551155256325 - the country code is 55 for BR | getPhoneNumber(): ?string | setPhoneNumber(?string phoneNumber): void |
| `referenceId` | `?string` | Optional | A second ID used to associate the team member with an entity in another system. | getReferenceId(): ?string | setReferenceId(?string referenceId): void |
| `status` | `?string` | Optional | Describes the status of the team member. | getStatus(): ?string | setStatus(?string status): void |
| `updatedAt` | `?string` | Optional | The timestamp, in RFC 3339 format, describing when the team member was last updated.<br>For example, "2018-10-04T04:00:00-07:00" or "2019-02-05T12:00:00Z". | getUpdatedAt(): ?string | setUpdatedAt(?string updatedAt): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\TeamMemberBuilder;
use SquareConnectAPILib\Models\Builders\TeamMemberAssignedLocationsBuilder;

$teamMember = TeamMemberBuilder::init()
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
    ->createdAt('created_at0')
    ->emailAddress('email_address0')
    ->familyName('family_name4')
    ->givenName('given_name4')
    ->build();
```

