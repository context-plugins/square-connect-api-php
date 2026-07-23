
# Batch Retrieve Orders Request

Defines the fields that are included in requests to the
`BatchRetrieveOrders` endpoint.

## Structure

`BatchRetrieveOrdersRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `locationId` | `?string` | Optional | The ID of the location for these orders. This field is optional: omit it to retrieve<br>orders within the scope of the current authorization's merchant ID. | getLocationId(): ?string | setLocationId(?string locationId): void |
| `orderIds` | `string[]` | Required | The IDs of the orders to retrieve. A maximum of 100 orders can be retrieved per request.<br><br>**Constraints**: *Minimum Length*: `1` | getOrderIds(): array | setOrderIds(array orderIds): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\BatchRetrieveOrdersRequestBuilder;

$batchRetrieveOrdersRequest = BatchRetrieveOrdersRequestBuilder::init(
    [
        'order_ids7'
    ]
)
    ->locationId('location_id6')
    ->build();
```

