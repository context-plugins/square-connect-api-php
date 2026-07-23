
# Snippet Response

## Structure

`SnippetResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `snippet` | [`?Snippet`](../../doc/models/snippet.md) | Optional | Represents the snippet that is added to a Square Online site. The snippet code is injected into the `head` element of all pages on the site, except for checkout pages. | getSnippet(): ?Snippet | setSnippet(?Snippet snippet): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\SnippetResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\SnippetBuilder;

$snippetResponse = SnippetResponseBuilder::init()
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
            'content4'
        )
            ->createdAt('created_at8')
            ->id('id0')
            ->siteId('site_id6')
            ->updatedAt('updated_at4')
            ->build()
    )
    ->build();
```

