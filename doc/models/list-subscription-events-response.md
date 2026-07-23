
# List Subscription Events Response

Defines the fields that are included in the response from the
[ListSubscriptionEvents](https://developer.squareup.com/reference/square_2021-08-18/subscriptions-api/list-subscription-events)
endpoint.

## Structure

`ListSubscriptionEventsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cursor` | `?string` | Optional | When a response is truncated, it includes a cursor that you can<br>use in a subsequent request to fetch the next set of events.<br>If empty, this is the final response.<br><br>For more information, see [Pagination](https://developer.squareup.com/docs/working-with-apis/pagination). | getCursor(): ?string | setCursor(?string cursor): void |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Information about errors encountered during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `subscriptionEvents` | [`?(SubscriptionEvent[])`](../../doc/models/subscription-event.md) | Optional | The `SubscriptionEvents` retrieved. | getSubscriptionEvents(): ?array | setSubscriptionEvents(?array subscriptionEvents): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\ListSubscriptionEventsResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\SubscriptionEventBuilder;
use SquareConnectAPILib\ApiHelper;

$listSubscriptionEventsResponse = ListSubscriptionEventsResponseBuilder::init()
    ->cursor('cursor4')
    ->errors(
        [
            ErrorBuilder::init(
                'category8',
                'code8'
            )
                ->detail('detail6')
                ->field('field4')
                ->build(),
            ErrorBuilder::init(
                'category8',
                'code8'
            )
                ->detail('detail6')
                ->field('field4')
                ->build(),
            ErrorBuilder::init(
                'category8',
                'code8'
            )
                ->detail('detail6')
                ->field('field4')
                ->build()
        ]
    )
    ->subscriptionEvents(
        [
            SubscriptionEventBuilder::init(
                '2020-04-24',
                '06809161-3867-4598-8269-8aea5be4f9de',
                '6JHXF3B2CW3YKHDV4XEM674H',
                'START_SUBSCRIPTION'
            )
                ->info(ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build(),
            SubscriptionEventBuilder::init(
                '2020-05-06',
                'a0c08083-5db0-4800-85c7-d398de4fbb6e',
                '6JHXF3B2CW3YKHDV4XEM674H',
                'STOP_SUBSCRIPTION'
            )
                ->info(ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build()
        ]
    )
    ->build();
```

