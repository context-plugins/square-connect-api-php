
# List Customer Groups Response

Defines the fields that are included in the response body of
a request to the [ListCustomerGroups](https://developer.squareup.com/reference/square_2021-08-18/customer-groups-api/list-customer-groups) endpoint.

Either `errors` or `groups` is present in a given response (never both).

## Structure

`ListCustomerGroupsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cursor` | `?string` | Optional | A pagination cursor to retrieve the next set of results for your<br>original query to the endpoint. This value is present only if the request<br>succeeded and additional results are available.<br><br>For more information, see [Pagination](https://developer.squareup.com/docs/working-with-apis/pagination). | getCursor(): ?string | setCursor(?string cursor): void |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `groups` | [`?(CustomerGroup[])`](../../doc/models/customer-group.md) | Optional | A list of customer groups belonging to the current seller. | getGroups(): ?array | setGroups(?array groups): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\ListCustomerGroupsResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\CustomerGroupBuilder;

$listCustomerGroupsResponse = ListCustomerGroupsResponseBuilder::init()
    ->cursor('cursor2')
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
    ->groups(
        [
            CustomerGroupBuilder::init(
                'Loyal Customers'
            )
                ->createdAt('2020-04-13T21:54:57.863Z')
                ->id('2TAT3CMH4Q0A9M87XJZED0WMR3')
                ->updatedAt('2020-04-13T21:54:58Z')
                ->build(),
            CustomerGroupBuilder::init(
                'Super Loyal Customers'
            )
                ->createdAt('2020-04-13T21:55:18.795Z')
                ->id('4XMEHESXJBNE9S9JAKZD2FGB14')
                ->updatedAt('2020-04-13T21:55:19Z')
                ->build()
        ]
    )
    ->build();
```

