
# V1 List Orders Request

## Structure

`V1ListOrdersRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `batchToken` | `?string` | Optional | A pagination cursor to retrieve the next set of results for your<br>original query to the endpoint. | getBatchToken(): ?string | setBatchToken(?string batchToken): void |
| `limit` | `?int` | Optional | The maximum number of payments to return in a single response. This value cannot exceed 200. | getLimit(): ?int | setLimit(?int limit): void |
| `order` | `?string` | Optional | The order in which payments are listed in the response. | getOrder(): ?string | setOrder(?string order): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\V1ListOrdersRequestBuilder;

$v1ListOrdersRequest = V1ListOrdersRequestBuilder::init()
    ->batchToken('batch_token4')
    ->limit(0)
    ->order('order8')
    ->build();
```

