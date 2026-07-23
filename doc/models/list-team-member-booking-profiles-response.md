
# List Team Member Booking Profiles Response

## Structure

`ListTeamMemberBookingProfilesResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cursor` | `?string` | Optional | The cursor for paginating through the results. | getCursor(): ?string | setCursor(?string cursor): void |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `teamMemberBookingProfiles` | [`?(TeamMemberBookingProfile[])`](../../doc/models/team-member-booking-profile.md) | Optional | The list of team member booking profiles. | getTeamMemberBookingProfiles(): ?array | setTeamMemberBookingProfiles(?array teamMemberBookingProfiles): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\ListTeamMemberBookingProfilesResponseBuilder;
use SquareConnectAPILib\Models\Builders\TeamMemberBookingProfileBuilder;

$listTeamMemberBookingProfilesResponse = ListTeamMemberBookingProfilesResponseBuilder::init()
    ->cursor('cursor2')
    ->errors(
        []
    )
    ->teamMemberBookingProfiles(
        [
            TeamMemberBookingProfileBuilder::init()
                ->description('description4')
                ->displayName('Sandbox Seller')
                ->isBookable(true)
                ->profileImageUrl('profile_image_url2')
                ->teamMemberId('TMXUrsBWWcHTt79t')
                ->build(),
            TeamMemberBookingProfileBuilder::init()
                ->description('description4')
                ->displayName('Sandbox Staff')
                ->isBookable(true)
                ->profileImageUrl('profile_image_url2')
                ->teamMemberId('TMaJcbiRqPIGZuS9')
                ->build()
        ]
    )
    ->build();
```

