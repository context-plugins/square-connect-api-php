# V1 Employees

```php
$v1EmployeesController = $client->getV1EmployeesController();
```

## Class Name

`V1EmployeesController`

## Methods

* [List Employees](../../doc/controllers/v1-employees.md#list-employees)
* [Create Employee](../../doc/controllers/v1-employees.md#create-employee)
* [Retrieve Employee](../../doc/controllers/v1-employees.md#retrieve-employee)
* [Update Employee](../../doc/controllers/v1-employees.md#update-employee)
* [List Employee Roles](../../doc/controllers/v1-employees.md#list-employee-roles)
* [Create Employee Role](../../doc/controllers/v1-employees.md#create-employee-role)
* [Retrieve Employee Role](../../doc/controllers/v1-employees.md#retrieve-employee-role)
* [Update Employee Role](../../doc/controllers/v1-employees.md#update-employee-role)


# List Employees

Provides summary information for all of a business's employees.

```php
function listEmployees(
    ?string $order = null,
    ?string $beginUpdatedAt = null,
    ?string $endUpdatedAt = null,
    ?string $beginCreatedAt = null,
    ?string $endCreatedAt = null,
    ?string $status = null,
    ?string $externalId = null,
    ?int $limit = null,
    ?string $batchToken = null
): array
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `order` | `?string` | Query, Optional | The order in which employees are listed in the response, based on their created_at field.      Default value: ASC |
| `beginUpdatedAt` | `?string` | Query, Optional | If filtering results by their updated_at field, the beginning of the requested reporting period, in ISO 8601 format |
| `endUpdatedAt` | `?string` | Query, Optional | If filtering results by there updated_at field, the end of the requested reporting period, in ISO 8601 format. |
| `beginCreatedAt` | `?string` | Query, Optional | If filtering results by their created_at field, the beginning of the requested reporting period, in ISO 8601 format. |
| `endCreatedAt` | `?string` | Query, Optional | If filtering results by their created_at field, the end of the requested reporting period, in ISO 8601 format. |
| `status` | `?string` | Query, Optional | If provided, the endpoint returns only employee entities with the specified status (ACTIVE or INACTIVE). |
| `externalId` | `?string` | Query, Optional | If provided, the endpoint returns only employee entities with the specified external_id. |
| `limit` | `?int` | Query, Optional | The maximum integer number of employee entities to return in a single response. Default 100, maximum 200. |
| `batchToken` | `?string` | Query, Optional | A pagination cursor to retrieve the next set of results for your<br>original query to the endpoint. |

## Requires scope

### oauth2

`EMPLOYEES_READ`

## Response Type

**200**: Success

[`V1Employee[]`](../../doc/models/v1-employee.md)

## Example Usage

```php
$v1EmployeesController = $client->getV1EmployeesController();

try {
    $result = $v1EmployeesController->listEmployees();
    echo 'V1Employee[]:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Create Employee

Use the CreateEmployee endpoint to add an employee to a Square
account. Employees created with the Connect API have an initial status
of `INACTIVE`. Inactive employees cannot sign in to Square Point of Sale
until they are activated from the Square Dashboard. Employee status
cannot be changed with the Connect API.

Employee entities cannot be deleted. To disable employee profiles,
set the employee's status to <code>INACTIVE</code>

```php
function createEmployee(V1Employee $body): V1Employee
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`V1Employee`](../../doc/models/v1-employee.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`EMPLOYEES_WRITE`

## Response Type

**200**: Success

[`V1Employee`](../../doc/models/v1-employee.md)

## Example Usage

```php
$body = V1EmployeeBuilder::init(
    'first_name6',
    'last_name4'
)->build();

$v1EmployeesController = $client->getV1EmployeesController();

try {
    $result = $v1EmployeesController->createEmployee($body);
    echo 'V1Employee:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Retrieve Employee

Provides the details for a single employee.

```php
function retrieveEmployee(string $employeeId): V1Employee
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `employeeId` | `string` | Template, Required | The employee's ID. |

## Requires scope

### oauth2

`EMPLOYEES_READ`

## Response Type

**200**: Success

[`V1Employee`](../../doc/models/v1-employee.md)

## Example Usage

```php
$employeeId = 'employee_id0';

$v1EmployeesController = $client->getV1EmployeesController();

try {
    $result = $v1EmployeesController->retrieveEmployee($employeeId);
    echo 'V1Employee:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Update Employee

```php
function updateEmployee(string $employeeId, V1Employee $body): V1Employee
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `employeeId` | `string` | Template, Required | The ID of the role to modify. |
| `body` | [`V1Employee`](../../doc/models/v1-employee.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`EMPLOYEES_WRITE`

## Response Type

**200**: Success

[`V1Employee`](../../doc/models/v1-employee.md)

## Example Usage

```php
$employeeId = 'employee_id0';

$body = V1EmployeeBuilder::init(
    'first_name6',
    'last_name4'
)->build();

$v1EmployeesController = $client->getV1EmployeesController();

try {
    $result = $v1EmployeesController->updateEmployee(
        $employeeId,
        $body
    );
    echo 'V1Employee:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# List Employee Roles

Provides summary information for all of a business's employee roles.

```php
function listEmployeeRoles(?string $order = null, ?int $limit = null, ?string $batchToken = null): array
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `order` | `?string` | Query, Optional | The order in which employees are listed in the response, based on their created_at field.Default value: ASC |
| `limit` | `?int` | Query, Optional | The maximum integer number of employee entities to return in a single response. Default 100, maximum 200. |
| `batchToken` | `?string` | Query, Optional | A pagination cursor to retrieve the next set of results for your<br>original query to the endpoint. |

## Requires scope

### oauth2

`EMPLOYEES_READ`

## Response Type

**200**: Success

[`V1EmployeeRole[]`](../../doc/models/v1-employee-role.md)

## Example Usage

```php
$v1EmployeesController = $client->getV1EmployeesController();

try {
    $result = $v1EmployeesController->listEmployeeRoles();
    echo 'V1EmployeeRole[]:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Create Employee Role

Creates an employee role you can then assign to employees.

Square accounts can include any number of roles that can be assigned to
employees. These roles define the actions and permissions granted to an
employee with that role. For example, an employee with a "Shift Manager"
role might be able to issue refunds in Square Point of Sale, whereas an
employee with a "Clerk" role might not.

Roles are assigned with the [V1UpdateEmployee](https://developer.squareup.com/reference/square_2021-08-18/v1-employees-api/update-employee-role)
endpoint. An employee can have only one role at a time.

If an employee has no role, they have none of the permissions associated
with roles. All employees can accept payments with Square Point of Sale.

```php
function createEmployeeRole(V1EmployeeRole $body): V1EmployeeRole
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`V1EmployeeRole`](../../doc/models/v1-employee-role.md) | Body, Required | An EmployeeRole object with a name and permissions, and an optional owner flag. |

## Requires scope

### oauth2

`EMPLOYEES_WRITE`

## Response Type

**200**: Success

[`V1EmployeeRole`](../../doc/models/v1-employee-role.md)

## Example Usage

```php
$body = V1EmployeeRoleBuilder::init(
    'name6',
    [
        'permissions3',
        'permissions4',
        'permissions5'
    ]
)->build();

$v1EmployeesController = $client->getV1EmployeesController();

try {
    $result = $v1EmployeesController->createEmployeeRole($body);
    echo 'V1EmployeeRole:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Retrieve Employee Role

Provides the details for a single employee role.

```php
function retrieveEmployeeRole(string $roleId): V1EmployeeRole
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `roleId` | `string` | Template, Required | The role's ID. |

## Requires scope

### oauth2

`EMPLOYEES_READ`

## Response Type

**200**: Success

[`V1EmployeeRole`](../../doc/models/v1-employee-role.md)

## Example Usage

```php
$roleId = 'role_id6';

$v1EmployeesController = $client->getV1EmployeesController();

try {
    $result = $v1EmployeesController->retrieveEmployeeRole($roleId);
    echo 'V1EmployeeRole:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Update Employee Role

Modifies the details of an employee role.

```php
function updateEmployeeRole(string $roleId, V1EmployeeRole $body): V1EmployeeRole
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `roleId` | `string` | Template, Required | The ID of the role to modify. |
| `body` | [`V1EmployeeRole`](../../doc/models/v1-employee-role.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`EMPLOYEES_WRITE`

## Response Type

**200**: Success

[`V1EmployeeRole`](../../doc/models/v1-employee-role.md)

## Example Usage

```php
$roleId = 'role_id6';

$body = V1EmployeeRoleBuilder::init(
    'name6',
    [
        'permissions3',
        'permissions4',
        'permissions5'
    ]
)->build();

$v1EmployeesController = $client->getV1EmployeesController();

try {
    $result = $v1EmployeesController->updateEmployeeRole(
        $roleId,
        $body
    );
    echo 'V1EmployeeRole:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

