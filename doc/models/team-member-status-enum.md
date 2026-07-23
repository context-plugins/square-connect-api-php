
# Team Member Status Enum

Enumerates the possible statuses the team member can have within a business.

## Enumeration

`TeamMemberStatusEnum`

## Fields

| Name | Description |
|  --- | --- |
| `ACTIVE` | The team member can sign in to Point of Sale and the Seller Dashboard. |
| `INACTIVE` | The team member can no longer sign in to Point of Sale or the Seller Dashboard,<br>but the team member's sales reports remain available. |

## Example

```php
use SquareConnectAPILib\Models\TeamMemberStatusEnum;

$teamMemberStatus = TeamMemberStatusEnum::ACTIVE;
```

