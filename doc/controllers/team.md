# Team

```php
$teamController = $client->getTeamController();
```

## Class Name

`TeamController`

## Methods

* [Create Team Member](../../doc/controllers/team.md#create-team-member)
* [Bulk Create Team Members](../../doc/controllers/team.md#bulk-create-team-members)
* [Bulk Update Team Members](../../doc/controllers/team.md#bulk-update-team-members)
* [Search Team Members](../../doc/controllers/team.md#search-team-members)
* [Retrieve Team Member](../../doc/controllers/team.md#retrieve-team-member)
* [Update Team Member](../../doc/controllers/team.md#update-team-member)
* [Retrieve Wage Setting](../../doc/controllers/team.md#retrieve-wage-setting)
* [Update Wage Setting](../../doc/controllers/team.md#update-wage-setting)


# Create Team Member

Creates a single `TeamMember` object. The `TeamMember` object is returned on successful creates.
You must provide the following values in your request to this endpoint:

- `given_name`
- `family_name`

Learn about [Troubleshooting the Team API](https://developer.squareup.com/docs/team/troubleshooting#createteammember).

```php
function createTeamMember(CreateTeamMemberRequest $body): CreateTeamMemberResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`CreateTeamMemberRequest`](../../doc/models/create-team-member-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`EMPLOYEES_WRITE`

## Response Type

**200**: Success

[`CreateTeamMemberResponse`](../../doc/models/create-team-member-response.md)

## Example Usage

```php
$body = CreateTeamMemberRequestBuilder::init()->build();

$teamController = $client->getTeamController();

try {
    $result = $teamController->createTeamMember($body);
    echo 'CreateTeamMemberResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Bulk Create Team Members

Creates multiple `TeamMember` objects. The created `TeamMember` objects are returned on successful creates.
This process is non-transactional and processes as much of the request as possible. If one of the creates in
the request cannot be successfully processed, the request is not marked as failed, but the body of the response
contains explicit error information for the failed create.

Learn about [Troubleshooting the Team API](https://developer.squareup.com/docs/team/troubleshooting#bulk-create-team-members).

```php
function bulkCreateTeamMembers(BulkCreateTeamMembersRequest $body): BulkCreateTeamMembersResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`BulkCreateTeamMembersRequest`](../../doc/models/bulk-create-team-members-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`EMPLOYEES_WRITE`

## Response Type

**200**: Success

[`BulkCreateTeamMembersResponse`](../../doc/models/bulk-create-team-members-response.md)

## Example Usage

```php
$body = BulkCreateTeamMembersRequestBuilder::init(
    [
        'key0' => CreateTeamMemberRequestBuilder::init()->build()
    ]
)->build();

$teamController = $client->getTeamController();

try {
    $result = $teamController->bulkCreateTeamMembers($body);
    echo 'BulkCreateTeamMembersResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Bulk Update Team Members

Updates multiple `TeamMember` objects. The updated `TeamMember` objects are returned on successful updates.
This process is non-transactional and processes as much of the request as possible. If one of the updates in
the request cannot be successfully processed, the request is not marked as failed, but the body of the response
contains explicit error information for the failed update.
Learn about [Troubleshooting the Team API](https://developer.squareup.com/docs/team/troubleshooting#bulk-update-team-members).

```php
function bulkUpdateTeamMembers(BulkUpdateTeamMembersRequest $body): BulkUpdateTeamMembersResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`BulkUpdateTeamMembersRequest`](../../doc/models/bulk-update-team-members-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`EMPLOYEES_WRITE`

## Response Type

**200**: Success

[`BulkUpdateTeamMembersResponse`](../../doc/models/bulk-update-team-members-response.md)

## Example Usage

```php
$body = BulkUpdateTeamMembersRequestBuilder::init(
    [
        'key0' => UpdateTeamMemberRequestBuilder::init()->build()
    ]
)->build();

$teamController = $client->getTeamController();

try {
    $result = $teamController->bulkUpdateTeamMembers($body);
    echo 'BulkUpdateTeamMembersResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Search Team Members

Returns a paginated list of `TeamMember` objects for a business.
The list can be filtered by the following:

- location IDs
- `status`

```php
function searchTeamMembers(SearchTeamMembersRequest $body): SearchTeamMembersResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`SearchTeamMembersRequest`](../../doc/models/search-team-members-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`EMPLOYEES_READ`

## Response Type

**200**: Success

[`SearchTeamMembersResponse`](../../doc/models/search-team-members-response.md)

## Example Usage

```php
$body = SearchTeamMembersRequestBuilder::init()->build();

$teamController = $client->getTeamController();

try {
    $result = $teamController->searchTeamMembers($body);
    echo 'SearchTeamMembersResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Retrieve Team Member

Retrieves a `TeamMember` object for the given `TeamMember.id`.
Learn about [Troubleshooting the Team API](https://developer.squareup.com/docs/team/troubleshooting#retrieve-a-team-member).

```php
function retrieveTeamMember(string $teamMemberId): RetrieveTeamMemberResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `teamMemberId` | `string` | Template, Required | The ID of the team member to retrieve. |

## Requires scope

### oauth2

`EMPLOYEES_READ`

## Response Type

**200**: Success

[`RetrieveTeamMemberResponse`](../../doc/models/retrieve-team-member-response.md)

## Example Usage

```php
$teamMemberId = 'team_member_id0';

$teamController = $client->getTeamController();

try {
    $result = $teamController->retrieveTeamMember($teamMemberId);
    echo 'RetrieveTeamMemberResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Update Team Member

Updates a single `TeamMember` object. The `TeamMember` object is returned on successful updates.
Learn about [Troubleshooting the Team API](https://developer.squareup.com/docs/team/troubleshooting#update-a-team-member).

```php
function updateTeamMember(string $teamMemberId, UpdateTeamMemberRequest $body): UpdateTeamMemberResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `teamMemberId` | `string` | Template, Required | The ID of the team member to update. |
| `body` | [`UpdateTeamMemberRequest`](../../doc/models/update-team-member-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`EMPLOYEES_WRITE`

## Response Type

**200**: Success

[`UpdateTeamMemberResponse`](../../doc/models/update-team-member-response.md)

## Example Usage

```php
$teamMemberId = 'team_member_id0';

$body = UpdateTeamMemberRequestBuilder::init()->build();

$teamController = $client->getTeamController();

try {
    $result = $teamController->updateTeamMember(
        $teamMemberId,
        $body
    );
    echo 'UpdateTeamMemberResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Retrieve Wage Setting

Retrieves a `WageSetting` object for a team member specified
by `TeamMember.id`.
Learn about [Troubleshooting the Team API](https://developer.squareup.com/docs/team/troubleshooting#retrievewagesetting).

```php
function retrieveWageSetting(string $teamMemberId): RetrieveWageSettingResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `teamMemberId` | `string` | Template, Required | The ID of the team member for which to retrieve the wage setting. |

## Requires scope

### oauth2

`EMPLOYEES_READ`

## Response Type

**200**: Success

[`RetrieveWageSettingResponse`](../../doc/models/retrieve-wage-setting-response.md)

## Example Usage

```php
$teamMemberId = 'team_member_id0';

$teamController = $client->getTeamController();

try {
    $result = $teamController->retrieveWageSetting($teamMemberId);
    echo 'RetrieveWageSettingResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Update Wage Setting

Creates or updates a `WageSetting` object. The object is created if a
`WageSetting` with the specified `team_member_id` does not exist. Otherwise,
it fully replaces the `WageSetting` object for the team member.
The `WageSetting` is returned on a successful update.
Learn about [Troubleshooting the Team API](https://developer.squareup.com/docs/team/troubleshooting#create-or-update-a-wage-setting).

```php
function updateWageSetting(string $teamMemberId, UpdateWageSettingRequest $body): UpdateWageSettingResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `teamMemberId` | `string` | Template, Required | The ID of the team member for which to update the `WageSetting` object. |
| `body` | [`UpdateWageSettingRequest`](../../doc/models/update-wage-setting-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`EMPLOYEES_WRITE`

## Response Type

**200**: Success

[`UpdateWageSettingResponse`](../../doc/models/update-wage-setting-response.md)

## Example Usage

```php
$teamMemberId = 'team_member_id0';

$body = UpdateWageSettingRequestBuilder::init(
    WageSettingBuilder::init()->build()
)->build();

$teamController = $client->getTeamController();

try {
    $result = $teamController->updateWageSetting(
        $teamMemberId,
        $body
    );
    echo 'UpdateWageSettingResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

