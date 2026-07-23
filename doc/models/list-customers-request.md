
# List Customers Request

Defines the query parameters that can be included in a request to the
`ListCustomers` endpoint.

## Structure

`ListCustomersRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cursor` | `?string` | Optional | A pagination cursor returned by a previous call to this endpoint.<br>Provide this cursor to retrieve the next set of results for your original query.<br><br>For more information, see [Pagination](https://developer.squareup.com/docs/working-with-apis/pagination). | getCursor(): ?string | setCursor(?string cursor): void |
| `limit` | `?int` | Optional | The maximum number of results to return in a single page. This limit is advisory. The response might contain more or fewer results.<br>The limit is ignored if it is less than 1 or greater than 100. The default value is 100.<br><br>For more information, see [Pagination](https://developer.squareup.com/docs/working-with-apis/pagination).<br><br>**Constraints**: `>= 1`, `<= 100` | getLimit(): ?int | setLimit(?int limit): void |
| `sortField` | `?string` | Optional | Indicates how customers should be sorted.<br><br>The default value is `DEFAULT`. | getSortField(): ?string | setSortField(?string sortField): void |
| `sortOrder` | `?string` | Optional | Indicates whether customers should be sorted in ascending (`ASC`) or<br>descending (`DESC`) order.<br><br>The default value is `ASC`. | getSortOrder(): ?string | setSortOrder(?string sortOrder): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\ListCustomersRequestBuilder;

$listCustomersRequest = ListCustomersRequestBuilder::init()
    ->cursor('cursor0')
    ->limit(100)
    ->sortField('sort_field2')
    ->sortOrder('sort_order6')
    ->build();
```

