
# Search Team Members Filter

Represents a filter used in a search for `TeamMember` objects. `AND` logic is applied
between the individual fields, and `OR` logic is applied within list-based fields.
For example, setting this filter value:

```
filter = (locations_ids = ["A", "B"], status = ACTIVE)
```

returns only active team members assigned to either location "A" or "B".

## Structure

`SearchTeamMembersFilter`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `locationIds` | `?(string[])` | Optional | When present, filters by team members assigned to the specified locations.<br>When empty, includes team members assigned to any location. | getLocationIds(): ?array | setLocationIds(?array locationIds): void |
| `status` | `?string` | Optional | When present, filters by team members who match the given status.<br>When empty, includes team members of all statuses. | getStatus(): ?string | setStatus(?string status): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\SearchTeamMembersFilterBuilder;

$searchTeamMembersFilter = SearchTeamMembersFilterBuilder::init()
    ->locationIds(
        [
            'location_ids0',
            'location_ids1'
        ]
    )
    ->status('status2')
    ->build();
```

