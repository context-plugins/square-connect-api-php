
# Search Orders Fulfillment Filter

Filter based on [order fulfillment](https://developer.squareup.com/reference/square_2021-08-18/objects/OrderFulfillment) information.

## Structure

`SearchOrdersFulfillmentFilter`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `fulfillmentStates` | `?(string[])` | Optional | A list of [fulfillment states](https://developer.squareup.com/reference/square_2021-08-18/objects/OrderFulfillmentState) to filter<br>for. The list returns orders if any of its fulfillments match any of the<br>fulfillment states listed in this field. | getFulfillmentStates(): ?array | setFulfillmentStates(?array fulfillmentStates): void |
| `fulfillmentTypes` | `?(string[])` | Optional | A list of [fulfillment types](https://developer.squareup.com/reference/square_2021-08-18/enums/OrderFulfillmentType) to filter<br>for. The list returns orders if any of its fulfillments match any of the fulfillment types<br>listed in this field. | getFulfillmentTypes(): ?array | setFulfillmentTypes(?array fulfillmentTypes): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\SearchOrdersFulfillmentFilterBuilder;

$searchOrdersFulfillmentFilter = SearchOrdersFulfillmentFilterBuilder::init()
    ->fulfillmentStates(
        [
            'fulfillment_states2',
            'fulfillment_states3',
            'fulfillment_states4'
        ]
    )
    ->fulfillmentTypes(
        [
            'fulfillment_types7',
            'fulfillment_types8',
            'fulfillment_types9'
        ]
    )
    ->build();
```

