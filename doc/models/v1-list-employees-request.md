
# V1 List Employees Request

## Structure

`V1ListEmployeesRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `batchToken` | `?string` | Optional | A pagination cursor to retrieve the next set of results for your<br>original query to the endpoint. | getBatchToken(): ?string | setBatchToken(?string batchToken): void |
| `beginCreatedAt` | `?string` | Optional | If filtering results by their created_at field, the beginning of the requested reporting period, in ISO 8601 format. | getBeginCreatedAt(): ?string | setBeginCreatedAt(?string beginCreatedAt): void |
| `beginUpdatedAt` | `?string` | Optional | If filtering results by their updated_at field, the beginning of the requested reporting period, in ISO 8601 format | getBeginUpdatedAt(): ?string | setBeginUpdatedAt(?string beginUpdatedAt): void |
| `endCreatedAt` | `?string` | Optional | If filtering results by their created_at field, the end of the requested reporting period, in ISO 8601 format. | getEndCreatedAt(): ?string | setEndCreatedAt(?string endCreatedAt): void |
| `endUpdatedAt` | `?string` | Optional | If filtering results by there updated_at field, the end of the requested reporting period, in ISO 8601 format. | getEndUpdatedAt(): ?string | setEndUpdatedAt(?string endUpdatedAt): void |
| `externalId` | `?string` | Optional | If provided, the endpoint returns only employee entities with the specified external_id. | getExternalId(): ?string | setExternalId(?string externalId): void |
| `limit` | `?int` | Optional | The maximum integer number of employee entities to return in a single response. Default 100, maximum 200. | getLimit(): ?int | setLimit(?int limit): void |
| `order` | `?string` | Optional | The order in which employees are listed in the response, based on their created_at field.      Default value: ASC | getOrder(): ?string | setOrder(?string order): void |
| `status` | `?string` | Optional | If provided, the endpoint returns only employee entities with the specified status (ACTIVE or INACTIVE). | getStatus(): ?string | setStatus(?string status): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\V1ListEmployeesRequestBuilder;

$v1ListEmployeesRequest = V1ListEmployeesRequestBuilder::init()
    ->batchToken('batch_token6')
    ->beginCreatedAt('begin_created_at2')
    ->beginUpdatedAt('begin_updated_at4')
    ->endCreatedAt('end_created_at6')
    ->endUpdatedAt('end_updated_at4')
    ->build();
```

