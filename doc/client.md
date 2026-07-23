
# Client Class Documentation

The following parameters are configurable for the API Client:

| Parameter | Type | Description |
|  --- | --- | --- |
| timeout | `int` | Timeout for API calls in seconds.<br>*Default*: `0` |
| enableRetries | `bool` | Whether to enable retries and backoff feature.<br>*Default*: `false` |
| numberOfRetries | `int` | The number of retries to make.<br>*Default*: `0` |
| retryInterval | `float` | The retry time interval between the endpoint calls.<br>*Default*: `1` |
| backOffFactor | `float` | Exponential backoff factor to increase interval between retries.<br>*Default*: `2` |
| maximumRetryWaitTime | `int` | The maximum wait time in seconds for overall retrying requests.<br>*Default*: `0` |
| retryOnTimeout | `bool` | Whether to retry on request timeout.<br>*Default*: `true` |
| httpStatusCodesToRetry | `array` | Http status codes to retry against.<br>*Default*: `408, 413, 429, 500, 502, 503, 504, 521, 522, 524, 408, 413, 429, 500, 502, 503, 504, 521, 522, 524` |
| httpMethodsToRetry | `array` | Http methods to retry against.<br>*Default*: `'GET', 'PUT', 'GET', 'PUT'` |
| proxyConfiguration | [`ProxyConfigurationBuilder`](../doc/proxy-configuration-builder.md) | Represents the proxy configurations for API calls |
| oauth2Credentials | [`Oauth2Credentials`](auth/oauth-2-authorization-code-grant.md) | The Credentials Setter for OAuth 2 Authorization Code Grant |
| oauth2ClientSecretCredentials | [`Oauth2ClientSecretCredentials`](auth/custom-header-signature.md) | The Credentials Setter for Custom Header Signature |

The API client can be initialized as follows:

```php
use SquareConnectAPILib\Authentication\Oauth2CredentialsBuilder;
use SquareConnectAPILib\Models\OAuthScopeOauth2Enum;
use SquareConnectAPILib\Authentication\Oauth2ClientSecretCredentialsBuilder;
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
    ->oauth2ClientSecretCredentials(
        Oauth2ClientSecretCredentialsBuilder::init(
            'Authorization'
        )
    )
    ->build();
```

## Square Connect API Client

The gateway for the SDK. This class acts as a factory for the Controllers and also holds the configuration of the SDK.

## Controllers

| Name | Description |
|  --- | --- |
| getMobileAuthorizationController() | Gets MobileAuthorizationController |
| getOAuthController() | Gets OAuthController |
| getV1EmployeesController() | Gets V1EmployeesController |
| getV1TransactionsController() | Gets V1TransactionsController |
| getApplePayController() | Gets ApplePayController |
| getBankAccountsController() | Gets BankAccountsController |
| getBookingsController() | Gets BookingsController |
| getCardsController() | Gets CardsController |
| getCashDrawersController() | Gets CashDrawersController |
| getCatalogController() | Gets CatalogController |
| getCustomersController() | Gets CustomersController |
| getCustomerGroupsController() | Gets CustomerGroupsController |
| getCustomerSegmentsController() | Gets CustomerSegmentsController |
| getDevicesController() | Gets DevicesController |
| getDisputesController() | Gets DisputesController |
| getEmployeesController() | Gets EmployeesController |
| getGiftCardsController() | Gets GiftCardsController |
| getGiftCardActivitiesController() | Gets GiftCardActivitiesController |
| getInventoryController() | Gets InventoryController |
| getInvoicesController() | Gets InvoicesController |
| getLaborController() | Gets LaborController |
| getLocationsController() | Gets LocationsController |
| getCheckoutController() | Gets CheckoutController |
| getTransactionsController() | Gets TransactionsController |
| getLoyaltyController() | Gets LoyaltyController |
| getMerchantsController() | Gets MerchantsController |
| getOrdersController() | Gets OrdersController |
| getPaymentsController() | Gets PaymentsController |
| getRefundsController() | Gets RefundsController |
| getSitesController() | Gets SitesController |
| getSnippetsController() | Gets SnippetsController |
| getSubscriptionsController() | Gets SubscriptionsController |
| getTeamController() | Gets TeamController |
| getTerminalController() | Gets TerminalController |
| getOAuthAuthorizationController() | Gets OAuthAuthorizationController |

