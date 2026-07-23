
# Search Terminal Refunds Request

## Structure

`SearchTerminalRefundsRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cursor` | `?string` | Optional | A pagination cursor returned by a previous call to this endpoint.<br>Provide this cursor to retrieve the next set of results for the original query. | getCursor(): ?string | setCursor(?string cursor): void |
| `limit` | `?int` | Optional | Limits the number of results returned for a single request.<br><br>**Constraints**: `>= 1`, `<= 100` | getLimit(): ?int | setLimit(?int limit): void |
| `query` | [`?TerminalRefundQuery`](../../doc/models/terminal-refund-query.md) | Optional | - | getQuery(): ?TerminalRefundQuery | setQuery(?TerminalRefundQuery query): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\SearchTerminalRefundsRequestBuilder;
use SquareConnectAPILib\Models\Builders\TerminalRefundQueryBuilder;
use SquareConnectAPILib\Models\Builders\TerminalRefundQueryFilterBuilder;
use SquareConnectAPILib\Models\Builders\TimeRangeBuilder;
use SquareConnectAPILib\Models\Builders\TerminalRefundQuerySortBuilder;

$searchTerminalRefundsRequest = SearchTerminalRefundsRequestBuilder::init()
    ->cursor('cursor2')
    ->limit(100)
    ->query(
        TerminalRefundQueryBuilder::init()
            ->filter(
                TerminalRefundQueryFilterBuilder::init()
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
                TerminalRefundQuerySortBuilder::init()
                    ->sortOrder('sort_order8')
                    ->build()
            )
            ->build()
    )
    ->build();
```

