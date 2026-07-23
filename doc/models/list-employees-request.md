
# List Employees Request

## Structure

`ListEmployeesRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cursor` | `?string` | Optional | The token required to retrieve the specified page of results. | getCursor(): ?string | setCursor(?string cursor): void |
| `limit` | `?int` | Optional | The number of employees to be returned on each page. | getLimit(): ?int | setLimit(?int limit): void |
| `locationId` | `?string` | Optional | - | getLocationId(): ?string | setLocationId(?string locationId): void |
| `status` | `?string` | Optional | Specifies the EmployeeStatus to filter the employee by. | getStatus(): ?string | setStatus(?string status): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\ListEmployeesRequestBuilder;

$listEmployeesRequest = ListEmployeesRequestBuilder::init()
    ->cursor('cursor8')
    ->limit(130)
    ->locationId('location_id8')
    ->status('status6')
    ->build();
```

