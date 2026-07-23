
# Delete Customer Group Response

Defines the fields that are included in the response body of
a request to the [DeleteCustomerGroup](https://developer.squareup.com/reference/square_2021-08-18/customer-groups-api/delete-customer-group) endpoint.

## Structure

`DeleteCustomerGroupResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\DeleteCustomerGroupResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;

$deleteCustomerGroupResponse = DeleteCustomerGroupResponseBuilder::init()
    ->errors(
        [
            ErrorBuilder::init(
                'category8',
                'code8'
            )
                ->detail('detail6')
                ->field('field4')
                ->build()
        ]
    )
    ->build();
```

