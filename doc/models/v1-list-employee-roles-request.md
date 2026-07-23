
# V1 List Employee Roles Request

## Structure

`V1ListEmployeeRolesRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `batchToken` | `?string` | Optional | A pagination cursor to retrieve the next set of results for your<br>original query to the endpoint. | getBatchToken(): ?string | setBatchToken(?string batchToken): void |
| `limit` | `?int` | Optional | The maximum integer number of employee entities to return in a single response. Default 100, maximum 200. | getLimit(): ?int | setLimit(?int limit): void |
| `order` | `?string` | Optional | The order in which employees are listed in the response, based on their created_at field.Default value: ASC | getOrder(): ?string | setOrder(?string order): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\V1ListEmployeeRolesRequestBuilder;

$v1ListEmployeeRolesRequest = V1ListEmployeeRolesRequestBuilder::init()
    ->batchToken('batch_token2')
    ->limit(12)
    ->order('order2')
    ->build();
```

