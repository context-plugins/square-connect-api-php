
# Upsert Snippet Response

Represents an `UpsertSnippet` response. The response can include either `snippet` or `errors`.

## Structure

`UpsertSnippetResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `snippet` | [`?Snippet`](../../doc/models/snippet.md) | Optional | Represents the snippet that is added to a Square Online site. The snippet code is injected into the `head` element of all pages on the site, except for checkout pages. | getSnippet(): ?Snippet | setSnippet(?Snippet snippet): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\UpsertSnippetResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\SnippetBuilder;

$upsertSnippetResponse = UpsertSnippetResponseBuilder::init()
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
    ->snippet(
        SnippetBuilder::init(
            '<script>var js = 1;</script>'
        )
            ->createdAt('2021-03-11T25:40:09Z')
            ->id('snippet_5d178150-a6c0-11eb-a9f1-437e6a2881e7')
            ->siteId('site_278075276488921835')
            ->updatedAt('2021-03-11T25:40:09Z')
            ->build()
    )
    ->build();
```

