
# OAuth 2 Authorization Code Grant



Documentation for accessing and setting credentials for oauth2.

## Auth Credentials

| Name | Type | Description | Setter | Getter |
|  --- | --- | --- | --- | --- |
| OAuthClientId | `string` | OAuth 2 Client ID | `oAuthClientId` | `getOAuthClientId()` |
| OAuthClientSecret | `string` | OAuth 2 Client Secret | `oAuthClientSecret` | `getOAuthClientSecret()` |
| OAuthRedirectUri | `string` | OAuth 2 Redirection endpoint or Callback Uri | `oAuthRedirectUri` | `getOAuthRedirectUri()` |
| OAuthToken | `OAuthToken\|null` | Object for storing information about the OAuth token | `oAuthToken` | `getOAuthToken()` |
| OAuthScopes | `string[]\|null` | List of scopes that apply to the OAuth token | `oAuthScopes` | `getOAuthScopes()` |
| OAuthClockSkew | `int` | Clock skew time in seconds applied while checking the OAuth Token expiry. | `oAuthClockSkew` | - |



**Note:** Auth credentials can be set using `Oauth2CredentialsBuilder::init()` in `oauth2Credentials` method in the client builder and accessed through `getOauth2Credentials` method in the client instance.

## Usage Example

### 1\. Client Initialization

You must initialize the client with *OAuth 2.0 Authorization Code Grant* credentials as shown in the following code snippet.

```php
use SquareConnectAPILib\Authentication\Oauth2CredentialsBuilder;
use SquareConnectAPILib\Models\OAuthScopeOauth2Enum;
use SquareConnectAPILib\SquareConnectAPIClientBuilder;

$client = SquareConnectAPIClientBuilder::init()
    ->oauth2Credentials(
        Oauth2CredentialsBuilder::init(
            'OAuthClientId',
            'OAuthClientSecret',
            'OAuthRedirectUri'
        )
            ->oAuthScopes(
                [
                    OAuthScopeOauth2Enum::APPOINTMENTS_BUSINESS_SETTINGS_READ,
                    OAuthScopeOauth2Enum::APPOINTMENTS_READ
                ]
            )
    )
    ->build();
```



Your application must obtain user authorization before it can execute an endpoint call in case this SDK chooses to use *OAuth 2.0 Authorization Code Grant*. This authorization includes the following steps

### 2\. Obtain user consent

To obtain user's consent, you must redirect the user to the authorization page.The `buildAuthorizationUrl()` method creates the URL to the authorization page. You must have initialized the client with scopes for which you need permission to access.

```php
$authUrl = $client->getOauth2Credentials()->buildAuthorizationUrl();
header('Location: ' . filter_var($authUrl, FILTER_SANITIZE_URL));
```

### 3\. Handle the OAuth server response

Once the user responds to the consent request, the OAuth 2.0 server responds to your application's access request by redirecting the user to the redirect URI specified set in `Configuration`.

If the user approves the request, the authorization code will be sent as the `code` query string:

```
https://example.com/oauth/callback?code=XXXXXXXXXXXXXXXXXXXXXXXXX
```

If the user does not approve the request, the response contains an `error` query string:

```
https://example.com/oauth/callback?error=access_denied
```

### 4\. Authorize the client using the code

After the server receives the code, it can exchange this for an *access token*. The access token is an object containing information for authorizing client requests and refreshing the token itself.

```php
try {
    $token = $client->getOauth2Credentials()->fetchToken($_GET['code']);
    // re-build the client with oauth token
    $client = $client
        ->toBuilder()
        ->oauth2Credentials($client->getOauth2CredentialsBuilder()->oAuthToken($token))
        ->build();
} catch (SquareConnectAPILib\Exceptions\ApiException $e) {
    // handle exception
}
```

### Scopes

Scopes enable your application to only request access to the resources it needs while enabling users to control the amount of access they grant to your application. Available scopes are defined in the [`OAuthScopeOauth2Enum`](../../doc/models/o-auth-scope-oauth-2-enum.md) enumeration.

| Scope Name | Description |
|  --- | --- |
| `APPOINTMENTS_BUSINESS_SETTINGS_READ` | __HTTP Method__: `GET`<br><br>Grants read access to booking business settings. For example, to call the<br>ListTeamMemberBookingProfiles endpoint. |
| `APPOINTMENTS_READ` | __HTTP Method__: `GET`, `POST`<br><br>Grants read access to booking information. For example, to call the<br>RetrieveBooking endpoint. |
| `APPOINTMENTS_WRITE` | __HTTP Method__: `POST`, `PUT`, `DELETE`<br><br>Grants write access to booking information. For example, to call the CreateBooking endpoint. |
| `BANK_ACCOUNTS_READ` | __HTTP Method__: `GET`<br><br>Grants read access to bank account information associated with the targeted<br>Square account. For example, to call the Connect v1 ListBankAccounts endpoint. |
| `CASH_DRAWER_READ` | __HTTP Method__: `GET`<br><br>Grants read access to cash drawer shift information. For example, to call the<br>ListCashDrawerShifts endpoint. |
| `CUSTOMERS_READ` | __HTTP Method__: `GET`<br><br>Grants read access to customer information. For example, to call the<br>ListCustomers endpoint. |
| `CUSTOMERS_WRITE` | __HTTP Method__: `POST`, `PUT`, `DELETE`<br><br>Grants write access to customer information. For example, to create and update<br>customer profiles. |
| `DEVICE_CREDENTIAL_MANAGEMENT` | __HTTP Method__: `POST`, `GET`<br><br>Grants read/write access to device credentials information. For example, to<br>call the CreateDeviceCode endpoint. |
| `DISPUTES_READ` | __HTTP Method__: `GET`<br><br>Grants read access to dispute information. For example, to call the RetrieveDispute<br>endpoint. |
| `DISPUTES_WRITE` | __HTTP Method__: `POST`, `PUT`, `DELETE`<br><br>Grants write access to dispute information. For example, to call the SubmitEvidence<br>endpoint. |
| `EMPLOYEES_READ` | __HTTP Method__: `GET`<br><br>Grants read access to employee profile information. For example, to call the<br>Connect v1 Employees API. |
| `EMPLOYEES_WRITE` | __HTTP Method__: `POST`, `PUT`, `DELETE`<br><br>Grants write access to employee profile information. For example, to create<br>and modify employee profiles. |
| `GIFTCARDS_READ` | __HTTP Method__: `GET`, `POST`<br><br>Grants read access to gift card information. For example, to call the RetrieveGiftCard<br>endpoint. |
| `GIFTCARDS_WRITE` | __HTTP Method__: `POST`, `PUT`, `DELETE`<br><br>Grants write access to gift card information. For example, to call the CreateGiftCard<br>endpoint. |
| `INVENTORY_READ` | __HTTP Method__: `GET`<br><br>Grants read access to inventory information. For example, to call the<br>RetrieveInventoryCount endpoint. |
| `INVENTORY_WRITE` | __HTTP Method__:  `POST`, `PUT`, `DELETE`<br><br>Grants write access to inventory information. For example, to call the<br>BatchChangeInventory endpoint. |
| `INVOICES_READ` | __HTTP Method__: `GET`, `POST`<br><br>Grants read access to invoice information. For example, to call the ListInvoices endpoint. |
| `INVOICES_WRITE` | __HTTP Method__: `POST`, `PUT`, `DELETE`<br><br>Grants write access to invoice information. For example, to call the CreateInvoice endpoint. |
| `ITEMS_READ` | __HTTP Method__: `GET`<br><br>Grants read access to business and location information. For example, to<br>obtain a location ID for subsequent activity. |
| `ITEMS_WRITE` | __HTTP Method__: `POST`, `PUT`, `DELETE`<br><br>Grants write access to product catalog information. For example, to modify or<br>add to a product catalog. |
| `LOYALTY_READ` | __HTTP Method__: `GET`<br><br>Grants read access to loyalty information. For example, to call the<br>ListLoyaltyPrograms endpoint. |
| `LOYALTY_WRITE` | __HTTP Method__: `POST`, `PUT`, `DELETE`<br><br>Grants write access to loyalty information. For example, to call the<br>CreateLoyaltyAccount endpoint. |
| `MERCHANT_PROFILE_READ` | __HTTP Method__: `GET`<br><br>Grants read access to business and location information. For example, to<br>obtain a location ID for subsequent activity. |
| `MERCHANT_PROFILE_WRITE` | *Originally missing* |
| `ONLINE_STORE_SITE_READ` | __HTTP Method__: `GET`, `POST`<br><br>Read access to ECOM online store site details. |
| `ONLINE_STORE_SNIPPETS_READ` | __HTTP Method__: `GET`, `POST`<br><br>Read access to ECOM online store snippets on published websites. |
| `ONLINE_STORE_SNIPPETS_WRITE` | __HTTP Method__: `POST`, `PUT`, `DELETE`<br><br>Write access to ECOM online store snippets on published websites. |
| `ORDERS_READ` | __HTTP Method__: `GET`<br><br>Grants read access to order information. For example, to call the<br>BatchRetrieveOrders endpoint. |
| `ORDERS_WRITE` | __HTTP Method__: `POST`, `PUT`, `DELETE`<br><br>Grants write access to order information. For example, to call the<br>CreateCheckout endpoint. |
| `PAYMENTS_READ` | __HTTP Method__: `GET`<br><br>Grants read access to transaction and refund information. For example, to call<br>the RetrieveTransaction endpoint. |
| `PAYMENTS_WRITE` | __HTTP Method__: `POST`, `PUT`, `DELETE`<br><br>Grants write access to transaction and refunds information. For example, to<br>process payments with the Payments or Checkout API. |
| `PAYMENTS_WRITE_ADDITIONAL_RECIPIENTS` | __HTTP Method__: `POST`, `PUT`, `DELETE`<br><br>Allow third party applications to deduct a portion of each transaction amount.<br>__Required__ to use multiparty transaction functionality with the Payments<br>API. |
| `PAYMENTS_WRITE_IN_PERSON` | __HTTP Method__: `POST`, `PUT`, `DELETE`<br><br>Grants write access to payments and refunds information. For example, to<br>process in-person payments. |
| `PAYMENTS_WRITE_SHARED_ONFILE` | __HTTP Method__: `POST`, `PUT`, `DELETE`<br><br>Allows the developer to process payments on behalf of a seller using a shared on file payment method. |
| `SETTLEMENTS_READ` | __HTTP Method__: `GET`<br><br>Grants read access to settlement (deposit) information. For example, to call<br>the Connect v1 ListSettlements endpoint. |
| `SUBSCRIPTIONS_READ` | __HTTP Method__: `GET`, `POST`<br><br>Grants read access to subscription information. For example, to call the RetrieveSubscription<br>endpoint. |
| `SUBSCRIPTIONS_WRITE` | __HTTP Method__: `POST`, `PUT`, `DELETE`<br><br>Grants write access to subscription information. For example, to call the CreateSubscription<br>endpoint. |
| `TIMECARDS_READ` | __HTTP Method__: `GET`<br><br>Grants read access to employee timecard information. For example, to call the<br>Connect v2 SearchShifts endpoint. |
| `TIMECARDS_SETTINGS_READ` | __HTTP Method__: `GET`<br><br>Grants read access to employee timecard settings information. For example, to<br>call the GetBreakType endpoint. |
| `TIMECARDS_SETTINGS_WRITE` | __HTTP Method__: `POST`, `PUT`, `DELETE`<br><br>Grants write access to employee timecard settings information. For example, to<br>call the UpdateBreakType endpoint. |
| `TIMECARDS_WRITE` | __HTTP Method__: `POST`, `PUT`, `DELETE`<br><br>Grants write access to employee shift information. For example, to create<br>and modify employee shifts. |

### Refreshing the token

An access token may expire after sometime. To extend its lifetime, you must refresh the token.

```php
if ($client->getOauth2Credentials()->isTokenExpired()) {
    try {
        $token = $client->getOauth2Credentials()->refreshToken();
        // re-build the client with oauth token
        $client = $client
            ->toBuilder()
            ->oauth2Credentials($client->getOauth2CredentialsBuilder()->oAuthToken($token))
            ->build();
    } catch (SquareConnectAPILib\Exceptions\ApiException $e) {
        // handle exception
    }
}
```

If a token expires, an exception will be thrown before the next endpoint call requiring authentication.

### Storing an access token for reuse

It is recommended that you store the access token for reuse.

```php
// store token
$_SESSION['access_token'] = $client->getOauth2Credentials()->getOAuthToken();
```

### Creating a client from a stored token

To authorize a client using a stored access token, just set the access token in Configuration along with the other configuration parameters before creating the client:

```php
// load token later...
$token = $_SESSION['access_token'];

// re-build the client with oauth token
$client = $client->toBuilder()->oauth2Credentials($client->getOauth2CredentialsBuilder()->oAuthToken($token))->build();
```

### Complete example



```php
<?php
require_once __DIR__.'/vendor/autoload.php';

session_start();

use SquareConnectAPILib\Authentication\Oauth2CredentialsBuilder;
use SquareConnectAPILib\Models\OAuthScopeOauth2Enum;
use SquareConnectAPILib\SquareConnectAPIClientBuilder;

$client = SquareConnectAPIClientBuilder::init()
    ->oauth2Credentials(
        Oauth2CredentialsBuilder::init(
            'OAuthClientId',
            'OAuthClientSecret',
            'OAuthRedirectUri'
        )
            ->oAuthScopes(
                [
                    OAuthScopeOauth2Enum::APPOINTMENTS_BUSINESS_SETTINGS_READ,
                    OAuthScopeOauth2Enum::APPOINTMENTS_READ
                ]
            )
    )
    ->build();


// Obtain access token, restore from cache if possible
if (isset($_SESSION['access_token'])) {
    $token = $_SESSION['access_token'];
    // re-build the client with oauth token
    $client = $client
        ->toBuilder()
        ->oauth2Credentials($client->getOauth2CredentialsBuilder()->oAuthToken($token))
        ->build();
} else {
    try {
        // build authorization url to redirect the user
        $oAuthRedirectUri = $client->getOauth2Credentials()->buildAuthorizationUrl();
        // redirect the user to $oAuthRedirectUri and get a code after the user consent
        header('Location: ' . filter_var($oAuthRedirectUri, FILTER_SANITIZE_URL));

        // fetch an oauth token to authorize the client using the stored code
        $token = $client->getOauth2Credentials()->fetchToken($_GET['code']);
        // re-build the client with oauth token
        $client = $client
            ->toBuilder()
            ->oauth2Credentials($client->getOauth2CredentialsBuilder()->oAuthToken($token))
            ->build();

        // store token
        $_SESSION['access_token'] = $token;
    } catch (SquareConnectAPILib\Exceptions\ApiException $e) {
        // handle exception
    }
}

// check if token gets expired, then try to refresh the token
if ($client->getOauth2Credentials()->isTokenExpired()) {
    try {
        // refresh the token
        $token = $client->getOauth2Credentials()->refreshToken();
        // re-build the client with oauth token
        $client = $client
            ->toBuilder()
            ->oauth2Credentials($client->getOauth2CredentialsBuilder()->oAuthToken($token))
            ->build();

        // update the cached token
        $_SESSION['access_token'] = $token;
    } catch (SquareConnectAPILib\Exceptions\ApiException $e) {
        // handle exception
    }
}

// the client is now authorized; you can use $client to make endpoint calls
```


