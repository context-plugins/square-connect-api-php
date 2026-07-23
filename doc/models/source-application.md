
# Source Application

Provides information about the application used to generate a change.

## Structure

`SourceApplication`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `applicationId` | `?string` | Optional | Read-only Square ID assigned to the application. Only used for<br>[Product](https://developer.squareup.com/reference/square_2021-08-18/enums/Product) type `EXTERNAL_API`. | getApplicationId(): ?string | setApplicationId(?string applicationId): void |
| `name` | `?string` | Optional | Read-only display name assigned to the application<br>(e.g. `"Custom Application"`, `"Square POS 4.74 for Android"`). | getName(): ?string | setName(?string name): void |
| `product` | `?string` | Optional | Read-only [Product](https://developer.squareup.com/reference/square_2021-08-18/enums/Product) type for the application. | getProduct(): ?string | setProduct(?string product): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\SourceApplicationBuilder;

$sourceApplication = SourceApplicationBuilder::init()
    ->applicationId('application_id4')
    ->name('name0')
    ->product('product0')
    ->build();
```

