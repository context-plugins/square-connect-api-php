
# Upsert Snippet Request

Represents an `UpsertSnippet` request.

## Structure

`UpsertSnippetRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `snippet` | [`Snippet`](../../doc/models/snippet.md) | Required | Represents the snippet that is added to a Square Online site. The snippet code is injected into the `head` element of all pages on the site, except for checkout pages. | getSnippet(): Snippet | setSnippet(Snippet snippet): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\UpsertSnippetRequestBuilder;
use SquareConnectAPILib\Models\Builders\SnippetBuilder;

$upsertSnippetRequest = UpsertSnippetRequestBuilder::init(
    SnippetBuilder::init(
        'content4'
    )
        ->createdAt('created_at8')
        ->id('id0')
        ->siteId('site_id6')
        ->updatedAt('updated_at4')
        ->build()
)->build();
```

