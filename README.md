
# Getting Started with Square Connect API

## Introduction

Client library for accessing the Square Connect APIs

Read the official documentation here:: [https://docs.connect.squareup.com/](https://docs.connect.squareup.com/)

## Building

The generated code has dependencies over external libraries like UniRest and JsonMapper. JsonMapper requires docblock annotations like `@var`, `@maps`, and `@factory` to map JSON responses with our class definitions. Hence the docblocks in generated code cannot be disabled by deactivating the PHP configurations like `opcache.save_comments`. These dependencies are defined in the `composer.json` file that comes with the SDK. To resolve these dependencies, we use the Composer package manager which requires PHP greater than or equal to 7.2 installed in your system. Visit [https://getcomposer.org/download/](https://getcomposer.org/download/) to download the installer file for Composer and run it in your system. Open command prompt and type `composer --version`. This should display the current version of the Composer installed if the installation was successful.

* Using command line, navigate to the directory containing the generated files (including `composer.json`) for the SDK.
* Run the command `composer install`. This should install all the required dependencies and create the `vendor` directory in your project directory.

![Building SDK - Step 1](https://apidocs.io/illustration/php?workspaceFolder=SquareConnectAPI&step=installDependencies)

### Configuring CURL Certificate Path in php.ini

:information_source: **Note** This is for Windows users only.

CURL used to include a list of accepted CAs, but no longer bundles ANY CA certs. So by default it will reject all SSL certificates as unverifiable. You will have to get your CA's cert and point curl at it. The steps are as follows:

1. Download the certificate bundle (.pem file) from [https://curl.haxx.se/docs/caextract.html](https://curl.haxx.se/docs/caextract.html) on to your system.
2. Add curl.cainfo = "PATH_TO/cacert.pem" to your php.ini file located in your php installation. “PATH_TO” must be an absolute path containing the .pem file.

```
[curl]; A default value for the CURLOPT_CAINFO option. This is required to be an
; absolute path.
curl.cainfo = PATH_TO/cacert.pem
```

## Installation

The following section explains how to use the SquareConnectAPILib library in a new project.

### 1. Open Project in an IDE

Open an IDE for PHP like PhpStorm. The basic workflow presented here is also applicable if you prefer using a different editor or IDE.

![Open project in PHPStorm - Step 1](https://apidocs.io/illustration/php?workspaceFolder=SquareConnectAPI&step=openIDE)

Click on `Open` in PhpStorm to browse to your generated SDK directory and then click `OK`.

![Open project in PHPStorm - Step 2](https://apidocs.io/illustration/php?workspaceFolder=SquareConnectAPI&step=openProject0)

### 2. Add a new Test Project

Create a new directory by right clicking on the solution name as shown below:

![Add a new project in PHPStorm - Step 1](https://apidocs.io/illustration/php?workspaceFolder=SquareConnectAPI&step=createDirectory)

Name the directory as "test".

![Add a new project in PHPStorm - Step 2](https://apidocs.io/illustration/php?workspaceFolder=SquareConnectAPI&step=nameDirectory)

Add a PHP file to this project.

![Add a new project in PHPStorm - Step 3](https://apidocs.io/illustration/php?workspaceFolder=SquareConnectAPI&step=createFile)

Name it "testSDK".

![Add a new project in PHPStorm - Step 4](https://apidocs.io/illustration/php?workspaceFolder=SquareConnectAPI&step=nameFile)

Depending on your project setup, you might need to include composer's autoloader in your PHP code to enable auto loading of classes.

```php
require_once "vendor/autoload.php";
```

It is important that the path inside require_once correctly points to the file `autoload.php` inside the vendor directory created during dependency installations.

![Add a new project in PHPStorm - Step 5](https://apidocs.io/illustration/php?workspaceFolder=SquareConnectAPI&step=projectFiles)

After this you can add code to initialize the client library and acquire the instance of a Controller class. Sample code to initialize the client library and use the Controller methods is given in the subsequent sections.

### 3. Run the Test Project

To run your project you must set the Interpreter for your project. Interpreter is the PHP engine installed on your computer.

Open `Settings` from `File` menu.

![Run Test Project - Step 1](https://apidocs.io/illustration/php?workspaceFolder=SquareConnectAPI&step=openSettings)

Select `PHP` from within `Languages & Frameworks`.

![Run Test Project - Step 2](https://apidocs.io/illustration/php?workspaceFolder=SquareConnectAPI&step=setInterpreter0)

Browse for Interpreters near the `Interpreter` option and choose your interpreter.

![Run Test Project - Step 3](https://apidocs.io/illustration/php?workspaceFolder=SquareConnectAPI&step=setInterpreter1)

Once the interpreter is selected, click `OK`.

![Run Test Project - Step 4](https://apidocs.io/illustration/php?workspaceFolder=SquareConnectAPI&step=setInterpreter2)

To run your project, right click on your PHP file inside your Test project and click on `Run`.

![Run Test Project - Step 5](https://apidocs.io/illustration/php?workspaceFolder=SquareConnectAPI&step=runProject)

## Test the SDK

Unit tests in this SDK can be run using PHPUnit.

1. First install the dependencies using composer including the `require-dev` dependencies.
2. Run `vendor\bin\phpunit --verbose` from commandline to execute tests. If you have installed PHPUnit globally, run tests using `phpunit --verbose` instead.

You can change the PHPUnit test configuration in the `phpunit.xml` file.

## Initialize the API Client

**_Note:_** Documentation for the client can be found [here.](doc/client.md)

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
| proxyConfiguration | [`ProxyConfigurationBuilder`](doc/proxy-configuration-builder.md) | Represents the proxy configurations for API calls |
| oauth2Credentials | [`Oauth2Credentials`](doc/auth/oauth-2-authorization-code-grant.md) | The Credentials Setter for OAuth 2 Authorization Code Grant |
| oauth2ClientSecretCredentials | [`Oauth2ClientSecretCredentials`](doc/auth/custom-header-signature.md) | The Credentials Setter for Custom Header Signature |

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

## Authorization

This API uses the following authentication schemes.

* [`oauth2 (OAuth 2 Authorization Code Grant)`](doc/auth/oauth-2-authorization-code-grant.md)
* [`oauth2ClientSecret (Custom Header Signature)`](doc/auth/custom-header-signature.md)

## List of APIs

* [Mobile Authorization](doc/controllers/mobile-authorization.md)
* [O Auth](doc/controllers/o-auth.md)
* [V1 Employees](doc/controllers/v1-employees.md)
* [V1 Transactions](doc/controllers/v1-transactions.md)
* [Apple Pay](doc/controllers/apple-pay.md)
* [Bank Accounts](doc/controllers/bank-accounts.md)
* [Bookings](doc/controllers/bookings.md)
* [Cards](doc/controllers/cards.md)
* [Cash Drawers](doc/controllers/cash-drawers.md)
* [Catalog](doc/controllers/catalog.md)
* [Customers](doc/controllers/customers.md)
* [Customer Groups](doc/controllers/customer-groups.md)
* [Customer Segments](doc/controllers/customer-segments.md)
* [Devices](doc/controllers/devices.md)
* [Disputes](doc/controllers/disputes.md)
* [Employees](doc/controllers/employees.md)
* [Gift Cards](doc/controllers/gift-cards.md)
* [Gift Card Activities](doc/controllers/gift-card-activities.md)
* [Inventory](doc/controllers/inventory.md)
* [Invoices](doc/controllers/invoices.md)
* [Labor](doc/controllers/labor.md)
* [Locations](doc/controllers/locations.md)
* [Checkout](doc/controllers/checkout.md)
* [Transactions](doc/controllers/transactions.md)
* [Loyalty](doc/controllers/loyalty.md)
* [Merchants](doc/controllers/merchants.md)
* [Orders](doc/controllers/orders.md)
* [Payments](doc/controllers/payments.md)
* [Refunds](doc/controllers/refunds.md)
* [Sites](doc/controllers/sites.md)
* [Snippets](doc/controllers/snippets.md)
* [Subscriptions](doc/controllers/subscriptions.md)
* [Team](doc/controllers/team.md)
* [Terminal](doc/controllers/terminal.md)

## SDK Infrastructure

### Configuration

* [ProxyConfigurationBuilder](doc/proxy-configuration-builder.md)

### HTTP

* [HttpRequest](doc/http-request.md)
* [HttpResponse](doc/http-response.md)

### Utilities

* [ApiException](doc/api-exception.md)

