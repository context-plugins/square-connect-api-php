
# Create Mobile Authorization Code Request

Defines the body parameters that can be provided in a request to the
__CreateMobileAuthorizationCode__ endpoint.

## Structure

`CreateMobileAuthorizationCodeRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `locationId` | `?string` | Optional | The Square location ID the authorization code should be tied to.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `191` | getLocationId(): ?string | setLocationId(?string locationId): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CreateMobileAuthorizationCodeRequestBuilder;

$createMobileAuthorizationCodeRequest = CreateMobileAuthorizationCodeRequestBuilder::init()
    ->locationId('location_id2')
    ->build();
```

