
# Loyalty Event Query

Represents a query used to search for loyalty events.

## Structure

`LoyaltyEventQuery`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `filter` | [`?LoyaltyEventFilter`](../../doc/models/loyalty-event-filter.md) | Optional | The filtering criteria. If the request specifies multiple filters,<br>the endpoint uses a logical AND to evaluate them. | getFilter(): ?LoyaltyEventFilter | setFilter(?LoyaltyEventFilter filter): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\LoyaltyEventQueryBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyEventFilterBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyEventDateTimeFilterBuilder;
use SquareConnectAPILib\Models\Builders\TimeRangeBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyEventLocationFilterBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyEventLoyaltyAccountFilterBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyEventOrderFilterBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyEventTypeFilterBuilder;

$loyaltyEventQuery = LoyaltyEventQueryBuilder::init()
    ->filter(
        LoyaltyEventFilterBuilder::init()
            ->dateTimeFilter(
                LoyaltyEventDateTimeFilterBuilder::init(
                    TimeRangeBuilder::init()
                        ->endAt('end_at8')
                        ->startAt('start_at4')
                        ->build()
                )->build()
            )
            ->locationFilter(
                LoyaltyEventLocationFilterBuilder::init(
                    [
                        'location_ids0',
                        'location_ids1',
                        'location_ids2'
                    ]
                )->build()
            )
            ->loyaltyAccountFilter(
                LoyaltyEventLoyaltyAccountFilterBuilder::init(
                    'loyalty_account_id8'
                )->build()
            )
            ->orderFilter(
                LoyaltyEventOrderFilterBuilder::init(
                    'order_id2'
                )->build()
            )
            ->typeFilter(
                LoyaltyEventTypeFilterBuilder::init(
                    [
                        'types5',
                        'types6',
                        'types7'
                    ]
                )->build()
            )->build()
    )->build();
```

