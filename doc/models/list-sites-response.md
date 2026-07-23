
# List Sites Response

Represents a `ListSites` response. The response can include either `sites` or `errors`.

## Structure

`ListSitesResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `sites` | [`?(Site[])`](../../doc/models/site.md) | Optional | The sites that belong to the seller. | getSites(): ?array | setSites(?array sites): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\ListSitesResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\SiteBuilder;

$listSitesResponse = ListSitesResponseBuilder::init()
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
                ->build()
        ]
    )
    ->sites(
        [
            SiteBuilder::init()
                ->createdAt('2020-02-28T13:22:51Z')
                ->domain('mysite1.square.site')
                ->id('site_278075276488921835')
                ->isPublished(true)
                ->siteTitle('My First Site')
                ->updatedAt('2021-01-13T09:58:32Z')
                ->build(),
            SiteBuilder::init()
                ->createdAt('2020-06-18T17:45:13Z')
                ->domain('mysite2.square.site')
                ->id('site_102725345836253849')
                ->isPublished(true)
                ->siteTitle('My Second Site')
                ->updatedAt('2020-11-23T02:19:10Z')
                ->build()
        ]
    )
    ->build();
```

