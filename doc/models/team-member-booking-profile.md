
# Team Member Booking Profile

The booking profile of a seller's team member, including the team member's ID, display name, description and whether the team member can be booked as a service provider.

## Structure

`TeamMemberBookingProfile`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `description` | `?string` | Optional | The description of the team member. | getDescription(): ?string | setDescription(?string description): void |
| `displayName` | `?string` | Optional | The display name of the team member. | getDisplayName(): ?string | setDisplayName(?string displayName): void |
| `isBookable` | `?bool` | Optional | Indicates whether the team member can be booked through the Bookings API or the seller's online booking channel or site (`true) or not (`false`). | getIsBookable(): ?bool | setIsBookable(?bool isBookable): void |
| `profileImageUrl` | `?string` | Optional | The URL of the team member's image for the bookings profile. | getProfileImageUrl(): ?string | setProfileImageUrl(?string profileImageUrl): void |
| `teamMemberId` | `?string` | Optional | The ID of the [TeamMember](https://developer.squareup.com/reference/square_2021-08-18/objects/TeamMember) object for the team member associated with the booking profile. | getTeamMemberId(): ?string | setTeamMemberId(?string teamMemberId): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\TeamMemberBookingProfileBuilder;

$teamMemberBookingProfile = TeamMemberBookingProfileBuilder::init()
    ->description('description0')
    ->displayName('display_name0')
    ->isBookable(false)
    ->profileImageUrl('profile_image_url6')
    ->teamMemberId('team_member_id0')
    ->build();
```

