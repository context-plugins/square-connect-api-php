# Sites

```php
$sitesController = $client->getSitesController();
```

## Class Name

`SitesController`


# List Sites

Lists the Square Online sites that belong to a seller.

__Note:__ Square Online APIs are publicly available as part of an early access program. For more information, see [Early access program for Square Online APIs](https://developer.squareup.com/docs/online-api#early-access-program-for-square-online-apis).

```php
function listSites(): ListSitesResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Requires scope

### oauth2

`ONLINE_STORE_SITE_READ`

## Response Type

**200**: Success

[`ListSitesResponse`](../../doc/models/list-sites-response.md)

## Example Usage

```php
$sitesController = $client->getSitesController();

try {
    $result = $sitesController->listSites();
    echo 'ListSitesResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

