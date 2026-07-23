
# Search Subscriptions Filter

Represents a set of SearchSubscriptionsQuery filters used to limit the set of Subscriptions returned by SearchSubscriptions.

## Structure

`SearchSubscriptionsFilter`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `customerIds` | `?(string[])` | Optional | A filter to select subscriptions based on the customer. | getCustomerIds(): ?array | setCustomerIds(?array customerIds): void |
| `locationIds` | `?(string[])` | Optional | A filter to select subscriptions based the location. | getLocationIds(): ?array | setLocationIds(?array locationIds): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\SearchSubscriptionsFilterBuilder;

$searchSubscriptionsFilter = SearchSubscriptionsFilterBuilder::init()
    ->customerIds(
        [
            'customer_ids5'
        ]
    )
    ->locationIds(
        [
            'location_ids8',
            'location_ids9'
        ]
    )
    ->build();
```

