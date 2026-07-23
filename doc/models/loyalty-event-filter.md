
# Loyalty Event Filter

The filtering criteria. If the request specifies multiple filters,
the endpoint uses a logical AND to evaluate them.

## Structure

`LoyaltyEventFilter`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `dateTimeFilter` | [`?LoyaltyEventDateTimeFilter`](../../doc/models/loyalty-event-date-time-filter.md) | Optional | Filter events by date time range. | getDateTimeFilter(): ?LoyaltyEventDateTimeFilter | setDateTimeFilter(?LoyaltyEventDateTimeFilter dateTimeFilter): void |
| `locationFilter` | [`?LoyaltyEventLocationFilter`](../../doc/models/loyalty-event-location-filter.md) | Optional | Filter events by location. | getLocationFilter(): ?LoyaltyEventLocationFilter | setLocationFilter(?LoyaltyEventLocationFilter locationFilter): void |
| `loyaltyAccountFilter` | [`?LoyaltyEventLoyaltyAccountFilter`](../../doc/models/loyalty-event-loyalty-account-filter.md) | Optional | Filter events by loyalty account. | getLoyaltyAccountFilter(): ?LoyaltyEventLoyaltyAccountFilter | setLoyaltyAccountFilter(?LoyaltyEventLoyaltyAccountFilter loyaltyAccountFilter): void |
| `orderFilter` | [`?LoyaltyEventOrderFilter`](../../doc/models/loyalty-event-order-filter.md) | Optional | Filter events by the order associated with the event. | getOrderFilter(): ?LoyaltyEventOrderFilter | setOrderFilter(?LoyaltyEventOrderFilter orderFilter): void |
| `typeFilter` | [`?LoyaltyEventTypeFilter`](../../doc/models/loyalty-event-type-filter.md) | Optional | Filter events by event type. | getTypeFilter(): ?LoyaltyEventTypeFilter | setTypeFilter(?LoyaltyEventTypeFilter typeFilter): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\LoyaltyEventFilterBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyEventDateTimeFilterBuilder;
use SquareConnectAPILib\Models\Builders\TimeRangeBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyEventLocationFilterBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyEventLoyaltyAccountFilterBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyEventOrderFilterBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyEventTypeFilterBuilder;

$loyaltyEventFilter = LoyaltyEventFilterBuilder::init()
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
    )->build();
```

