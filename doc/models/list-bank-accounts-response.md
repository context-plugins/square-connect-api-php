
# List Bank Accounts Response

Response object returned by ListBankAccounts.

## Structure

`ListBankAccountsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `bankAccounts` | [`?(BankAccount[])`](../../doc/models/bank-account.md) | Optional | List of BankAccounts associated with this account. | getBankAccounts(): ?array | setBankAccounts(?array bankAccounts): void |
| `cursor` | `?string` | Optional | When a response is truncated, it includes a cursor that you can<br>use in a subsequent request to fetch next set of bank accounts.<br>If empty, this is the final response.<br><br>For more information, see [Pagination](https://developer.squareup.com/docs/working-with-apis/pagination). | getCursor(): ?string | setCursor(?string cursor): void |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Information on errors encountered during the request. | getErrors(): ?array | setErrors(?array errors): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\ListBankAccountsResponseBuilder;
use SquareConnectAPILib\Models\Builders\BankAccountBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;

$listBankAccountsResponse = ListBankAccountsResponseBuilder::init()
    ->bankAccounts(
        [
            BankAccountBuilder::init(
                '971',
                'CHECKING',
                'US',
                false,
                'USD',
                false,
                'Jane Doe',
                'ao6iaQ9vhDiaQD7n3GB',
                '112200303',
                'VERIFICATION_IN_PROGRESS'
            )
                ->bankName('Bank Name')
                ->debitMandateReferenceId('debit_mandate_reference_id4')
                ->fingerprint('fingerprint6')
                ->locationId('S8GWD5example')
                ->referenceId('reference_id8')
                ->version(5)
                ->build(),
            BankAccountBuilder::init(
                '972',
                'CHECKING',
                'US',
                false,
                'USD',
                false,
                'Jane Doe',
                '4x7WXuaxrkQkVlka3GB',
                '112200303',
                'VERIFICATION_IN_PROGRESS'
            )
                ->bankName('Bank Name')
                ->debitMandateReferenceId('debit_mandate_reference_id4')
                ->fingerprint('fingerprint6')
                ->locationId('S8GWD5example')
                ->referenceId('reference_id8')
                ->version(5)
                ->build()
        ]
    )
    ->cursor('cursor2')
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
    ->build();
```

