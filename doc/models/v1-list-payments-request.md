
# V1 List Payments Request

## Structure

`V1ListPaymentsRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `batchToken` | `?string` | Optional | A pagination cursor to retrieve the next set of results for your<br>original query to the endpoint. | getBatchToken(): ?string | setBatchToken(?string batchToken): void |
| `beginTime` | `?string` | Optional | The beginning of the requested reporting period, in ISO 8601 format. If this value is before January 1, 2013 (2013-01-01T00:00:00Z), this endpoint returns an error. Default value: The current time minus one year. | getBeginTime(): ?string | setBeginTime(?string beginTime): void |
| `endTime` | `?string` | Optional | The end of the requested reporting period, in ISO 8601 format. If this value is more than one year greater than begin_time, this endpoint returns an error. Default value: The current time. | getEndTime(): ?string | setEndTime(?string endTime): void |
| `includePartial` | `?bool` | Optional | Indicates whether or not to include partial payments in the response. Partial payments will have the tenders collected so far, but the itemizations will be empty until the payment is completed. | getIncludePartial(): ?bool | setIncludePartial(?bool includePartial): void |
| `limit` | `?int` | Optional | The maximum number of payments to return in a single response. This value cannot exceed 200. | getLimit(): ?int | setLimit(?int limit): void |
| `order` | `?string` | Optional | The order in which payments are listed in the response. | getOrder(): ?string | setOrder(?string order): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\V1ListPaymentsRequestBuilder;

$v1ListPaymentsRequest = V1ListPaymentsRequestBuilder::init()
    ->batchToken('batch_token6')
    ->beginTime('begin_time6')
    ->endTime('end_time8')
    ->includePartial(false)
    ->limit(132)
    ->build();
```

