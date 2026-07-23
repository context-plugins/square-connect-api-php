
# V1 List Employees Response

## Structure

`V1ListEmployeesResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `items` | [`?(V1Employee[])`](../../doc/models/v1-employee.md) | Optional | - | getItems(): ?array | setItems(?array items): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\V1ListEmployeesResponseBuilder;
use SquareConnectAPILib\Models\Builders\V1EmployeeBuilder;

$v1ListEmployeesResponse = V1ListEmployeesResponseBuilder::init()
    ->items(
        [
            V1EmployeeBuilder::init(
                'first_name8',
                'last_name6'
            )
                ->authorizedLocationIds(
                    [
                        'authorized_location_ids9',
                        'authorized_location_ids0'
                    ]
                )
                ->createdAt('created_at6')
                ->email('email8')
                ->externalId('external_id4')
                ->id('id8')
                ->build(),
            V1EmployeeBuilder::init(
                'first_name8',
                'last_name6'
            )
                ->authorizedLocationIds(
                    [
                        'authorized_location_ids9',
                        'authorized_location_ids0'
                    ]
                )
                ->createdAt('created_at6')
                ->email('email8')
                ->externalId('external_id4')
                ->id('id8')
                ->build(),
            V1EmployeeBuilder::init(
                'first_name8',
                'last_name6'
            )
                ->authorizedLocationIds(
                    [
                        'authorized_location_ids9',
                        'authorized_location_ids0'
                    ]
                )
                ->createdAt('created_at6')
                ->email('email8')
                ->externalId('external_id4')
                ->id('id8')
                ->build()
        ]
    )
    ->build();
```

