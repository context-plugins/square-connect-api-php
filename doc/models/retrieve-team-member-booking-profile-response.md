
# Retrieve Team Member Booking Profile Response

## Structure

`RetrieveTeamMemberBookingProfileResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `teamMemberBookingProfile` | [`?TeamMemberBookingProfile`](../../doc/models/team-member-booking-profile.md) | Optional | The booking profile of a seller's team member, including the team member's ID, display name, description and whether the team member can be booked as a service provider. | getTeamMemberBookingProfile(): ?TeamMemberBookingProfile | setTeamMemberBookingProfile(?TeamMemberBookingProfile teamMemberBookingProfile): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\RetrieveTeamMemberBookingProfileResponseBuilder;
use SquareConnectAPILib\Models\Builders\TeamMemberBookingProfileBuilder;

$retrieveTeamMemberBookingProfileResponse = RetrieveTeamMemberBookingProfileResponseBuilder::init()
    ->errors(
        []
    )
    ->teamMemberBookingProfile(
        TeamMemberBookingProfileBuilder::init()
            ->description('description2')
            ->displayName('Sandbox Staff')
            ->isBookable(true)
            ->profileImageUrl('profile_image_url8')
            ->teamMemberId('TMaJcbiRqPIGZuS9')
            ->build()
    )
    ->build();
```

