
# Team Member Assigned Locations

An object that represents a team member's assignment to locations.

## Structure

`TeamMemberAssignedLocations`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `assignmentType` | `?string` | Optional | The current assignment type of the team member. | getAssignmentType(): ?string | setAssignmentType(?string assignmentType): void |
| `locationIds` | `?(string[])` | Optional | The locations that the team member is assigned to. | getLocationIds(): ?array | setLocationIds(?array locationIds): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\TeamMemberAssignedLocationsBuilder;

$teamMemberAssignedLocations = TeamMemberAssignedLocationsBuilder::init()
    ->assignmentType('assignment_type6')
    ->locationIds(
        [
            'location_ids6',
            'location_ids7',
            'location_ids8'
        ]
    )
    ->build();
```

