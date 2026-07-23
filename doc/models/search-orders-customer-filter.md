
# Search Orders Customer Filter

A filter based on the order `customer_id` and any tender `customer_id`
associated with the order. It does not filter based on the
[FulfillmentRecipient](https://developer.squareup.com/reference/square_2021-08-18/objects/OrderFulfillmentRecipient) `customer_id`.

## Structure

`SearchOrdersCustomerFilter`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `customerIds` | `?(string[])` | Optional | A list of customer IDs to filter by.<br><br>Max: 10 customer IDs. | getCustomerIds(): ?array | setCustomerIds(?array customerIds): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\SearchOrdersCustomerFilterBuilder;

$searchOrdersCustomerFilter = SearchOrdersCustomerFilterBuilder::init()
    ->customerIds(
        [
            'customer_ids3'
        ]
    )
    ->build();
```

