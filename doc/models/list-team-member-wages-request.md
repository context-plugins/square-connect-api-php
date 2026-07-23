
# List Team Member Wages Request

A request for a set of `TeamMemberWage` objects.

## Structure

`ListTeamMemberWagesRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cursor` | `?string` | Optional | A pointer to the next page of `EmployeeWage` results to fetch. | getCursor(): ?string | setCursor(?string cursor): void |
| `limit` | `?int` | Optional | The maximum number of `TeamMemberWage` results to return per page. The number can range between<br>1 and 200. The default is 200.<br><br>**Constraints**: `>= 1`, `<= 200` | getLimit(): ?int | setLimit(?int limit): void |
| `teamMemberId` | `?string` | Optional | Filter the returned wages to only those that are associated with the<br>specified team member. | getTeamMemberId(): ?string | setTeamMemberId(?string teamMemberId): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\ListTeamMemberWagesRequestBuilder;

$listTeamMemberWagesRequest = ListTeamMemberWagesRequestBuilder::init()
    ->cursor('cursor4')
    ->limit(28)
    ->teamMemberId('team_member_id2')
    ->build();
```

