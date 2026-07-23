
# Site

Represents a Square Online site, which is an online store for a Square seller.

## Structure

`Site`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `createdAt` | `?string` | Optional | The timestamp of when the site was created, in RFC 3339 format. | getCreatedAt(): ?string | setCreatedAt(?string createdAt): void |
| `domain` | `?string` | Optional | The domain of the site (without the protocol). For example, `mysite1.square.site`. | getDomain(): ?string | setDomain(?string domain): void |
| `id` | `?string` | Optional | The Square-assigned ID of the site.<br><br>**Constraints**: *Maximum Length*: `32` | getId(): ?string | setId(?string id): void |
| `isPublished` | `?bool` | Optional | Indicates whether the site is published. | getIsPublished(): ?bool | setIsPublished(?bool isPublished): void |
| `siteTitle` | `?string` | Optional | The title of the site. | getSiteTitle(): ?string | setSiteTitle(?string siteTitle): void |
| `updatedAt` | `?string` | Optional | The timestamp of when the site was last updated, in RFC 3339 format. | getUpdatedAt(): ?string | setUpdatedAt(?string updatedAt): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\SiteBuilder;

$site = SiteBuilder::init()
    ->createdAt('created_at2')
    ->domain('domain0')
    ->id('id4')
    ->isPublished(false)
    ->siteTitle('site_title0')
    ->build();
```

