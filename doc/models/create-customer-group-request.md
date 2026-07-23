
# Create Customer Group Request

Defines the body parameters that can be included in a request to the
[CreateCustomerGroup](https://developer.squareup.com/reference/square_2021-08-18/customer-groups-api/create-customer-group) endpoint.

## Structure

`CreateCustomerGroupRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `group` | [`CustomerGroup`](../../doc/models/customer-group.md) | Required | Represents a group of customer profiles.<br><br>Customer groups can be created, be modified, and have their membership defined using<br>the Customers API or within the Customer Directory in the Square Seller Dashboard or Point of Sale. | getGroup(): CustomerGroup | setGroup(CustomerGroup group): void |
| `idempotencyKey` | `?string` | Optional | The idempotency key for the request. For more information, see [Idempotency](https://developer.squareup.com/docs/basics/api101/idempotency). | getIdempotencyKey(): ?string | setIdempotencyKey(?string idempotencyKey): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CreateCustomerGroupRequestBuilder;
use SquareConnectAPILib\Models\Builders\CustomerGroupBuilder;

$createCustomerGroupRequest = CreateCustomerGroupRequestBuilder::init(
    CustomerGroupBuilder::init(
        'name8'
    )
        ->createdAt('created_at4')
        ->id('id8')
        ->updatedAt('updated_at6')
        ->build()
)
    ->idempotencyKey('idempotency_key4')
    ->build();
```

