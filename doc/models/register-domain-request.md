
# Register Domain Request

Defines the parameters that can be included in the body of
a request to the [RegisterDomain](https://developer.squareup.com/reference/square_2021-08-18/apple-pay-api/register-domain) endpoint.

## Structure

`RegisterDomainRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `domainName` | `string` | Required | A domain name as described in RFC-1034 that will be registered with ApplePay.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `255` | getDomainName(): string | setDomainName(string domainName): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\RegisterDomainRequestBuilder;

$registerDomainRequest = RegisterDomainRequestBuilder::init(
    'domain_name4'
)->build();
```

