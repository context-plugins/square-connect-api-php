# Snippets

```php
$snippetsController = $client->getSnippetsController();
```

## Class Name

`SnippetsController`

## Methods

* [Delete Snippet](../../doc/controllers/snippets.md#delete-snippet)
* [Retrieve Snippet](../../doc/controllers/snippets.md#retrieve-snippet)
* [Upsert Snippet](../../doc/controllers/snippets.md#upsert-snippet)


# Delete Snippet

Removes your snippet from a Square Online site.

You can call [ListSites](https://developer.squareup.com/reference/square_2021-08-18/sites-api/list-sites) to get the IDs of the sites that belong to a seller.

__Note:__ Square Online APIs are publicly available as part of an early access program. For more information, see [Early access program for Square Online APIs](https://developer.squareup.com/docs/online-api#early-access-program-for-square-online-apis).

```php
function deleteSnippet(string $siteId): DeleteSnippetResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `siteId` | `string` | Template, Required | The ID of the site that contains the snippet. |

## Requires scope

### oauth2

`ONLINE_STORE_SNIPPETS_WRITE`

## Response Type

**200**: Success

[`DeleteSnippetResponse`](../../doc/models/delete-snippet-response.md)

## Example Usage

```php
$siteId = 'site_id6';

$snippetsController = $client->getSnippetsController();

try {
    $result = $snippetsController->deleteSnippet($siteId);
    echo 'DeleteSnippetResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Retrieve Snippet

Retrieves your snippet from a Square Online site. A site can contain snippets from multiple snippet applications, but you can retrieve only the snippet that was added by your application.

You can call [ListSites](https://developer.squareup.com/reference/square_2021-08-18/sites-api/list-sites) to get the IDs of the sites that belong to a seller.

__Note:__ Square Online APIs are publicly available as part of an early access program. For more information, see [Early access program for Square Online APIs](https://developer.squareup.com/docs/online-api#early-access-program-for-square-online-apis).

```php
function retrieveSnippet(string $siteId): RetrieveSnippetResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `siteId` | `string` | Template, Required | The ID of the site that contains the snippet. |

## Requires scope

### oauth2

`ONLINE_STORE_SNIPPETS_READ`

## Response Type

**200**: Success

[`RetrieveSnippetResponse`](../../doc/models/retrieve-snippet-response.md)

## Example Usage

```php
$siteId = 'site_id6';

$snippetsController = $client->getSnippetsController();

try {
    $result = $snippetsController->retrieveSnippet($siteId);
    echo 'RetrieveSnippetResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Upsert Snippet

Adds a snippet to a Square Online site or updates the existing snippet on the site.
The snippet code is appended to the end of the `head` element on every page of the site, except checkout pages. A snippet application can add one snippet to a given site.

You can call [ListSites](https://developer.squareup.com/reference/square_2021-08-18/sites-api/list-sites) to get the IDs of the sites that belong to a seller.

__Note:__ Square Online APIs are publicly available as part of an early access program. For more information, see [Early access program for Square Online APIs](https://developer.squareup.com/docs/online-api#early-access-program-for-square-online-apis).

```php
function upsertSnippet(string $siteId, UpsertSnippetRequest $body): UpsertSnippetResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `siteId` | `string` | Template, Required | The ID of the site where you want to add or update the snippet. |
| `body` | [`UpsertSnippetRequest`](../../doc/models/upsert-snippet-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`ONLINE_STORE_SNIPPETS_WRITE`

## Response Type

**200**: Success

[`UpsertSnippetResponse`](../../doc/models/upsert-snippet-response.md)

## Example Usage

```php
$siteId = 'site_id6';

$body = UpsertSnippetRequestBuilder::init(
    SnippetBuilder::init(
        'content4'
    )->build()
)->build();

$snippetsController = $client->getSnippetsController();

try {
    $result = $snippetsController->upsertSnippet(
        $siteId,
        $body
    );
    echo 'UpsertSnippetResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

