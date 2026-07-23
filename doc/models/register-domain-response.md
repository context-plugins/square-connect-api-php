
# Register Domain Response

Defines the fields that are included in the response body of
a request to the [RegisterDomain](https://developer.squareup.com/reference/square_2021-08-18/apple-pay-api/register-domain) endpoint.

Either `errors` or `status` are present in a given response (never both).

## Structure

`RegisterDomainResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `status` | `?string` | Optional | The status of the domain registration.<br><br>See [RegisterDomainResponseStatus](https://developer.squareup.com/reference/square_2021-08-18/enums/RegisterDomainResponseStatus) for possible values. | getStatus(): ?string | setStatus(?string status): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\RegisterDomainResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;

$registerDomainResponse = RegisterDomainResponseBuilder::init()
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
    ->status('VERIFIED')
    ->build();
```

