
# V1 List Settlements Request

## Structure

`V1ListSettlementsRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `batchToken` | `?string` | Optional | A pagination cursor to retrieve the next set of results for your<br>original query to the endpoint. | getBatchToken(): ?string | setBatchToken(?string batchToken): void |
| `beginTime` | `?string` | Optional | The beginning of the requested reporting period, in ISO 8601 format. If this value is before January 1, 2013 (2013-01-01T00:00:00Z), this endpoint returns an error. Default value: The current time minus one year. | getBeginTime(): ?string | setBeginTime(?string beginTime): void |
| `endTime` | `?string` | Optional | The end of the requested reporting period, in ISO 8601 format. If this value is more than one year greater than begin_time, this endpoint returns an error. Default value: The current time. | getEndTime(): ?string | setEndTime(?string endTime): void |
| `limit` | `?int` | Optional | The maximum number of settlements to return in a single response. This value cannot exceed 200. | getLimit(): ?int | setLimit(?int limit): void |
| `order` | `?string` | Optional | The order in which settlements are listed in the response. | getOrder(): ?string | setOrder(?string order): void |
| `status` | `?string` | Optional | Provide this parameter to retrieve only settlements with a particular status (SENT or FAILED). | getStatus(): ?string | setStatus(?string status): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\V1ListSettlementsRequestBuilder;

$v1ListSettlementsRequest = V1ListSettlementsRequestBuilder::init()
    ->batchToken('batch_token8')
    ->beginTime('begin_time8')
    ->endTime('end_time6')
    ->limit(236)
    ->order('order2')
    ->build();
```

