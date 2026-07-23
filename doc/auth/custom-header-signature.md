
# Custom Header Signature



Documentation for accessing and setting credentials for oauth2ClientSecret.

## Auth Credentials

| Name | Type | Description | Setter | Getter |
|  --- | --- | --- | --- | --- |
| Authorization | `string` | - | `authorization` | `getAuthorization()` |



**Note:** Auth credentials can be set using `Oauth2ClientSecretCredentialsBuilder::init()` in `oauth2ClientSecretCredentials` method in the client builder and accessed through `getOauth2ClientSecretCredentials` method in the client instance.

## Usage Example

### Client Initialization

You must provide credentials in the client as shown in the following code snippet.

```php
use SquareConnectAPILib\Authentication\Oauth2ClientSecretCredentialsBuilder;
use SquareConnectAPILib\SquareConnectAPIClientBuilder;

$client = SquareConnectAPIClientBuilder::init()
    ->oauth2ClientSecretCredentials(
        Oauth2ClientSecretCredentialsBuilder::init(
            'Authorization'
        )
    )
    ->build();
```


