
# Search Team Members Request

Represents a search request for a filtered list of `TeamMember` objects.

## Structure

`SearchTeamMembersRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cursor` | `?string` | Optional | The opaque cursor for fetching the next page. For more information, see<br>[pagination](https://developer.squareup.com/docs/working-with-apis/pagination). | getCursor(): ?string | setCursor(?string cursor): void |
| `limit` | `?int` | Optional | The maximum number of `TeamMember` objects in a page (100 by default).<br><br>**Constraints**: `>= 1`, `<= 100` | getLimit(): ?int | setLimit(?int limit): void |
| `query` | [`?SearchTeamMembersQuery`](../../doc/models/search-team-members-query.md) | Optional | Represents the parameters in a search for `TeamMember` objects. | getQuery(): ?SearchTeamMembersQuery | setQuery(?SearchTeamMembersQuery query): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\SearchTeamMembersRequestBuilder;
use SquareConnectAPILib\Models\Builders\SearchTeamMembersQueryBuilder;
use SquareConnectAPILib\Models\Builders\SearchTeamMembersFilterBuilder;

$searchTeamMembersRequest = SearchTeamMembersRequestBuilder::init()
    ->cursor('cursor0')
    ->limit(100)
    ->query(
        SearchTeamMembersQueryBuilder::init()
            ->filter(
                SearchTeamMembersFilterBuilder::init()
                    ->locationIds(
                        [
                            'location_ids4'
                        ]
                    )
                    ->status('status6')
                    ->build()
            )
            ->build()
    )
    ->build();
```

