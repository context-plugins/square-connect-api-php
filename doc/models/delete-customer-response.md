
# Delete Customer Response

Defines the fields that are included in the response body of
a request to the `DeleteCustomer` endpoint.

## Structure

`DeleteCustomerResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\DeleteCustomerResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;

$deleteCustomerResponse = DeleteCustomerResponseBuilder::init()
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

