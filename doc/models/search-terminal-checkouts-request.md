
# Search Terminal Checkouts Request

## Structure

`SearchTerminalCheckoutsRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cursor` | `?string` | Optional | A pagination cursor returned by a previous call to this endpoint.<br>Provide this cursor to retrieve the next set of results for the original query.<br>See [Pagination](https://developer.squareup.com/docs/basics/api101/pagination) for more information. | getCursor(): ?string | setCursor(?string cursor): void |
| `limit` | `?int` | Optional | Limits the number of results returned for a single request.<br><br>**Constraints**: `>= 1`, `<= 100` | getLimit(): ?int | setLimit(?int limit): void |
| `query` | [`?TerminalCheckoutQuery`](../../doc/models/terminal-checkout-query.md) | Optional | - | getQuery(): ?TerminalCheckoutQuery | setQuery(?TerminalCheckoutQuery query): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\SearchTerminalCheckoutsRequestBuilder;
use SquareConnectAPILib\Models\Builders\TerminalCheckoutQueryBuilder;
use SquareConnectAPILib\Models\Builders\TerminalCheckoutQueryFilterBuilder;
use SquareConnectAPILib\Models\Builders\TimeRangeBuilder;
use SquareConnectAPILib\Models\Builders\TerminalCheckoutQuerySortBuilder;

$searchTerminalCheckoutsRequest = SearchTerminalCheckoutsRequestBuilder::init()
    ->cursor('cursor6')
    ->limit(100)
    ->query(
        TerminalCheckoutQueryBuilder::init()
            ->filter(
                TerminalCheckoutQueryFilterBuilder::init()
                    ->createdAt(
                        TimeRangeBuilder::init()
                            ->endAt('end_at8')
                            ->startAt('start_at4')
                            ->build()
                    )
                    ->deviceId('device_id0')
                    ->status('status6')
                    ->build()
            )
            ->sort(
                TerminalCheckoutQuerySortBuilder::init()
                    ->sortOrder('sort_order8')
                    ->build()
            )
            ->build()
    )
    ->build();
```

