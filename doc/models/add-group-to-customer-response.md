
# Add Group to Customer Response

Defines the fields that are included in the response body of
a request to the [AddGroupToCustomer](https://developer.squareup.com/reference/square_2021-08-18/customers-api/add-group-to-customer) endpoint.

## Structure

`AddGroupToCustomerResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\AddGroupToCustomerResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;

$addGroupToCustomerResponse = AddGroupToCustomerResponseBuilder::init()
    ->errors(
        [
            ErrorBuilder::init(
                'category8',
                'code8'
            )
                ->detail('detail6')
                ->field('field4')
                ->build(),
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

