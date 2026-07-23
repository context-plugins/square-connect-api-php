
# List Transactions Request

Defines the query parameters that can be included in
a request to the [ListTransactions](https://developer.squareup.com/reference/square_2021-08-18/transactions-api/list-transactions) endpoint.

Deprecated - recommend using [SearchOrders](https://developer.squareup.com/reference/square_2021-08-18/orders-api/search-orders)

## Structure

`ListTransactionsRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `beginTime` | `?string` | Optional | The beginning of the requested reporting period, in RFC 3339 format.<br><br>See [Date ranges](https://developer.squareup.com/docs/build-basics/working-with-dates) for details on date inclusivity/exclusivity.<br><br>Default value: The current time minus one year. | getBeginTime(): ?string | setBeginTime(?string beginTime): void |
| `cursor` | `?string` | Optional | A pagination cursor returned by a previous call to this endpoint.<br>Provide this to retrieve the next set of results for your original query.<br><br>See [Paginating results](https://developer.squareup.com/docs/working-with-apis/pagination) for more information. | getCursor(): ?string | setCursor(?string cursor): void |
| `endTime` | `?string` | Optional | The end of the requested reporting period, in RFC 3339 format.<br><br>See [Date ranges](https://developer.squareup.com/docs/build-basics/working-with-dates) for details on date inclusivity/exclusivity.<br><br>Default value: The current time. | getEndTime(): ?string | setEndTime(?string endTime): void |
| `sortOrder` | `?string` | Optional | The order in which results are listed in the response (`ASC` for<br>oldest first, `DESC` for newest first).<br><br>Default value: `DESC` | getSortOrder(): ?string | setSortOrder(?string sortOrder): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\ListTransactionsRequestBuilder;

$listTransactionsRequest = ListTransactionsRequestBuilder::init()
    ->beginTime('begin_time8')
    ->cursor('cursor6')
    ->endTime('end_time2')
    ->sortOrder('sort_order0')
    ->build();
```

