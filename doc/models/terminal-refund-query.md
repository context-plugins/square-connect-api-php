
# Terminal Refund Query

## Structure

`TerminalRefundQuery`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `filter` | [`?TerminalRefundQueryFilter`](../../doc/models/terminal-refund-query-filter.md) | Optional | - | getFilter(): ?TerminalRefundQueryFilter | setFilter(?TerminalRefundQueryFilter filter): void |
| `sort` | [`?TerminalRefundQuerySort`](../../doc/models/terminal-refund-query-sort.md) | Optional | - | getSort(): ?TerminalRefundQuerySort | setSort(?TerminalRefundQuerySort sort): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\TerminalRefundQueryBuilder;
use SquareConnectAPILib\Models\Builders\TerminalRefundQueryFilterBuilder;
use SquareConnectAPILib\Models\Builders\TimeRangeBuilder;
use SquareConnectAPILib\Models\Builders\TerminalRefundQuerySortBuilder;

$terminalRefundQuery = TerminalRefundQueryBuilder::init()
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
    ->build();
```

