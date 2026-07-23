
# Error

Represents an error encountered during a request to the Connect API.

See [Handling errors](https://developer.squareup.com/docs/build-basics/handling-errors) for more information.

## Structure

`Error`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `category` | `string` | Required | The high-level category for the error. | getCategory(): string | setCategory(string category): void |
| `code` | `string` | Required | The specific code of the error. | getCode(): string | setCode(string code): void |
| `detail` | `?string` | Optional | A human-readable description of the error for debugging purposes. | getDetail(): ?string | setDetail(?string detail): void |
| `field` | `?string` | Optional | The name of the field provided in the original request (if any) that<br>the error pertains to. | getField(): ?string | setField(?string field): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\ErrorBuilder;

$error = ErrorBuilder::init(
    'category2',
    'code2'
)
    ->detail('detail0')
    ->field('field8')
    ->build();
```

