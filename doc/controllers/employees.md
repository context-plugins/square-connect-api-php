# Employees

```php
$employeesController = $client->getEmployeesController();
```

## Class Name

`EmployeesController`

## Methods

* [List Employees](../../doc/controllers/employees.md#list-employees)
* [Retrieve Employee](../../doc/controllers/employees.md#retrieve-employee)


# List Employees

```php
function listEmployees(
    ?string $locationId = null,
    ?string $status = null,
    ?int $limit = null,
    ?string $cursor = null
): ListEmployeesResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `locationId` | `?string` | Query, Optional | - |
| `status` | `?string` | Query, Optional | Specifies the EmployeeStatus to filter the employee by. |
| `limit` | `?int` | Query, Optional | The number of employees to be returned on each page. |
| `cursor` | `?string` | Query, Optional | The token required to retrieve the specified page of results. |

## Requires scope

### oauth2

`EMPLOYEES_READ`

## Response Type

**200**: Success

[`ListEmployeesResponse`](../../doc/models/list-employees-response.md)

## Example Usage

```php
$employeesController = $client->getEmployeesController();

try {
    $result = $employeesController->listEmployees();
    echo 'ListEmployeesResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Retrieve Employee

```php
function retrieveEmployee(string $id): RetrieveEmployeeResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | UUID for the employee that was requested. |

## Requires scope

### oauth2

`EMPLOYEES_READ`

## Response Type

**200**: Success

[`RetrieveEmployeeResponse`](../../doc/models/retrieve-employee-response.md)

## Example Usage

```php
$id = 'id0';

$employeesController = $client->getEmployeesController();

try {
    $result = $employeesController->retrieveEmployee($id);
    echo 'RetrieveEmployeeResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

