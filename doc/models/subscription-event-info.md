
# Subscription Event Info

Provides information about the subscription event.

## Structure

`SubscriptionEventInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `code` | `?array` | Optional | - | getCode(): ?array | setCode(?array code): void |
| `detail` | `?string` | Optional | A human-readable explanation for the event. | getDetail(): ?string | setDetail(?string detail): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\SubscriptionEventInfoBuilder;
use SquareConnectAPILib\ApiHelper;

$subscriptionEventInfo = SubscriptionEventInfoBuilder::init()
    ->code(ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->detail('detail6')
    ->build();
```

