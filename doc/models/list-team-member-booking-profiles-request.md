
# List Team Member Booking Profiles Request

## Structure

`ListTeamMemberBookingProfilesRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `bookableOnly` | `?bool` | Optional | Indicates whether to include only bookable team members in the returned result (`true`) or not (`false`). | getBookableOnly(): ?bool | setBookableOnly(?bool bookableOnly): void |
| `cursor` | `?string` | Optional | The cursor for paginating through the results. | getCursor(): ?string | setCursor(?string cursor): void |
| `limit` | `?int` | Optional | The maximum number of results to return. | getLimit(): ?int | setLimit(?int limit): void |
| `locationId` | `?string` | Optional | Indicates whether to include only team members enabled at the given location in the returned result. | getLocationId(): ?string | setLocationId(?string locationId): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\ListTeamMemberBookingProfilesRequestBuilder;

$listTeamMemberBookingProfilesRequest = ListTeamMemberBookingProfilesRequestBuilder::init()
    ->bookableOnly(false)
    ->cursor('cursor8')
    ->limit(6)
    ->locationId('location_id2')
    ->build();
```

