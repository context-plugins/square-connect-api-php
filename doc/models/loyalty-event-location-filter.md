
# Loyalty Event Location Filter

Filter events by location.

## Structure

`LoyaltyEventLocationFilter`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `locationIds` | `string[]` | Required | The [location](https://developer.squareup.com/reference/square_2021-08-18/objects/Location) IDs for loyalty events to query.<br>If multiple values are specified, the endpoint uses<br>a logical OR to combine them.<br><br>**Constraints**: *Minimum Length*: `1` | getLocationIds(): array | setLocationIds(array locationIds): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\LoyaltyEventLocationFilterBuilder;

$loyaltyEventLocationFilter = LoyaltyEventLocationFilterBuilder::init(
    [
        'location_ids2',
        'location_ids3',
        'location_ids4'
    ]
)->build();
```

