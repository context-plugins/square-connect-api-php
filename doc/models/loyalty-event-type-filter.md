
# Loyalty Event Type Filter

Filter events by event type.

## Structure

`LoyaltyEventTypeFilter`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `types` | `string[]` | Required | The loyalty event types used to filter the result.<br>If multiple values are specified, the endpoint uses a<br>logical OR to combine them. | getTypes(): array | setTypes(array types): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\LoyaltyEventTypeFilterBuilder;

$loyaltyEventTypeFilter = LoyaltyEventTypeFilterBuilder::init(
    [
        'types3'
    ]
)->build();
```

