
# Remove Group from Customer Response

Defines the fields that are included in the response body of
a request to the [RemoveGroupFromCustomer](https://developer.squareup.com/reference/square_2021-08-18/customers-api/remove-group-from-customer)
endpoint.

## Structure

`RemoveGroupFromCustomerResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\RemoveGroupFromCustomerResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;

$removeGroupFromCustomerResponse = RemoveGroupFromCustomerResponseBuilder::init()
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

