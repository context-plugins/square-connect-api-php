
# Terminal Checkout Query

## Structure

`TerminalCheckoutQuery`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `filter` | [`?TerminalCheckoutQueryFilter`](../../doc/models/terminal-checkout-query-filter.md) | Optional | - | getFilter(): ?TerminalCheckoutQueryFilter | setFilter(?TerminalCheckoutQueryFilter filter): void |
| `sort` | [`?TerminalCheckoutQuerySort`](../../doc/models/terminal-checkout-query-sort.md) | Optional | - | getSort(): ?TerminalCheckoutQuerySort | setSort(?TerminalCheckoutQuerySort sort): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\TerminalCheckoutQueryBuilder;
use SquareConnectAPILib\Models\Builders\TerminalCheckoutQueryFilterBuilder;
use SquareConnectAPILib\Models\Builders\TimeRangeBuilder;
use SquareConnectAPILib\Models\Builders\TerminalCheckoutQuerySortBuilder;

$terminalCheckoutQuery = TerminalCheckoutQueryBuilder::init()
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
    ->build();
```

