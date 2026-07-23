
# V1 Update Employee Request

## Structure

`V1UpdateEmployeeRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `body` | [`V1Employee`](../../doc/models/v1-employee.md) | Required | Represents one of a business's employees. | getBody(): V1Employee | setBody(V1Employee body): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\V1UpdateEmployeeRequestBuilder;
use SquareConnectAPILib\Models\Builders\V1EmployeeBuilder;

$v1UpdateEmployeeRequest = V1UpdateEmployeeRequestBuilder::init(
    V1EmployeeBuilder::init(
        'first_name6',
        'last_name4'
    )
        ->authorizedLocationIds(
            [
                'authorized_location_ids7',
                'authorized_location_ids8'
            ]
        )
        ->createdAt('created_at4')
        ->email('email0')
        ->externalId('external_id2')
        ->id('id6')
        ->build()
)->build();
```

