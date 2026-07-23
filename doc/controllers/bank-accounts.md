# Bank Accounts

```php
$bankAccountsController = $client->getBankAccountsController();
```

## Class Name

`BankAccountsController`

## Methods

* [List Bank Accounts](../../doc/controllers/bank-accounts.md#list-bank-accounts)
* [Get Bank Account by V1 Id](../../doc/controllers/bank-accounts.md#get-bank-account-by-v1-id)
* [Get Bank Account](../../doc/controllers/bank-accounts.md#get-bank-account)


# List Bank Accounts

Returns a list of [BankAccount](https://developer.squareup.com/reference/square_2021-08-18/objects/BankAccount) objects linked to a Square account.

```php
function listBankAccounts(
    ?string $cursor = null,
    ?int $limit = null,
    ?string $locationId = null
): ListBankAccountsResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `cursor` | `?string` | Query, Optional | The pagination cursor returned by a previous call to this endpoint.<br>Use it in the next `ListBankAccounts` request to retrieve the next set<br>of results.<br><br>See the [Pagination](https://developer.squareup.com/docs/working-with-apis/pagination) guide for more information. |
| `limit` | `?int` | Query, Optional | Upper limit on the number of bank accounts to return in the response.<br>Currently, 1000 is the largest supported limit. You can specify a limit<br>of up to 1000 bank accounts. This is also the default limit. |
| `locationId` | `?string` | Query, Optional | Location ID. You can specify this optional filter<br>to retrieve only the linked bank accounts belonging to a specific location. |

## Requires scope

### oauth2

`BANK_ACCOUNTS_READ`

## Response Type

**200**: Success

[`ListBankAccountsResponse`](../../doc/models/list-bank-accounts-response.md)

## Example Usage

```php
$bankAccountsController = $client->getBankAccountsController();

try {
    $result = $bankAccountsController->listBankAccounts();
    echo 'ListBankAccountsResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Get Bank Account by V1 Id

Returns details of a [BankAccount](https://developer.squareup.com/reference/square_2021-08-18/objects/BankAccount) identified by V1 bank account ID.

```php
function getBankAccountByV1Id(string $v1BankAccountId): GetBankAccountByV1IdResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `v1BankAccountId` | `string` | Template, Required | Connect V1 ID of the desired `BankAccount`. For more information, see<br>[Retrieve a bank account by using an ID issued by V1 Bank Accounts API](https://developer.squareup.com/docs/bank-accounts-api#retrieve-a-bank-account-by-using-an-id-issued-by-v1-bank-accounts-api). |

## Requires scope

### oauth2

`BANK_ACCOUNTS_READ`

## Response Type

**200**: Success

[`GetBankAccountByV1IdResponse`](../../doc/models/get-bank-account-by-v1-id-response.md)

## Example Usage

```php
$v1BankAccountId = 'v1_bank_account_id8';

$bankAccountsController = $client->getBankAccountsController();

try {
    $result = $bankAccountsController->getBankAccountByV1Id($v1BankAccountId);
    echo 'GetBankAccountByV1IdResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Get Bank Account

Returns details of a [BankAccount](https://developer.squareup.com/reference/square_2021-08-18/objects/BankAccount)
linked to a Square account.

```php
function getBankAccount(string $bankAccountId): GetBankAccountResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `bankAccountId` | `string` | Template, Required | Square-issued ID of the desired `BankAccount`. |

## Requires scope

### oauth2

`BANK_ACCOUNTS_READ`

## Response Type

**200**: Success

[`GetBankAccountResponse`](../../doc/models/get-bank-account-response.md)

## Example Usage

```php
$bankAccountId = 'bank_account_id0';

$bankAccountsController = $client->getBankAccountsController();

try {
    $result = $bankAccountsController->getBankAccount($bankAccountId);
    echo 'GetBankAccountResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

