
# Team Member Invitation Status Enum

Enumerates the possible invitation statuses the team member can have within a business.

## Enumeration

`TeamMemberInvitationStatusEnum`

## Fields

| Name | Description |
|  --- | --- |
| `UNINVITED` | The team member has not received an invitation. |
| `PENDING` | The team member has received an invitation, but had not accepted it. |
| `ACCEPTED` | The team member has both received and accepted an invitation. |

## Example

```php
use SquareConnectAPILib\Models\TeamMemberInvitationStatusEnum;

$teamMemberInvitationStatus = TeamMemberInvitationStatusEnum::UNINVITED;
```

