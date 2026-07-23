
# Retrieve Customer Group Response

Defines the fields that are included in the response body of
a request to the [RetrieveCustomerGroup](https://developer.squareup.com/reference/square_2021-08-18/customer-groups-api/retrieve-customer-group) endpoint.

Either `errors` or `group` is present in a given response (never both).

## Structure

`RetrieveCustomerGroupResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `group` | [`?CustomerGroup`](../../doc/models/customer-group.md) | Optional | Represents a group of customer profiles.<br><br>Customer groups can be created, be modified, and have their membership defined using<br>the Customers API or within the Customer Directory in the Square Seller Dashboard or Point of Sale. | getGroup(): ?CustomerGroup | setGroup(?CustomerGroup group): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\RetrieveCustomerGroupResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\CustomerGroupBuilder;

$retrieveCustomerGroupResponse = RetrieveCustomerGroupResponseBuilder::init()
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
    ->group(
        CustomerGroupBuilder::init(
            'Loyal Customers'
        )
            ->createdAt('2020-04-13T21:54:57.863Z')
            ->id('2TAT3CMH4Q0A9M87XJZED0WMR3')
            ->updatedAt('2020-04-13T21:54:58Z')
            ->build()
    )
    ->build();
```

