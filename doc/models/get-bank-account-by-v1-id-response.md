
# Get Bank Account by V1 Id Response

Response object returned by GetBankAccountByV1Id.

## Structure

`GetBankAccountByV1IdResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `bankAccount` | [`?BankAccount`](../../doc/models/bank-account.md) | Optional | Represents a bank account. For more information about<br>linking a bank account to a Square account, see<br>[Bank Accounts API](https://developer.squareup.com/docs/bank-accounts-api). | getBankAccount(): ?BankAccount | setBankAccount(?BankAccount bankAccount): void |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Information on errors encountered during the request. | getErrors(): ?array | setErrors(?array errors): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\GetBankAccountByV1IdResponseBuilder;
use SquareConnectAPILib\Models\Builders\BankAccountBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;

$getBankAccountByV1IdResponse = GetBankAccountByV1IdResponseBuilder::init()
    ->bankAccount(
        BankAccountBuilder::init(
            '971',
            'CHECKING',
            'US',
            false,
            'USD',
            false,
            'Jane Doe',
            'w3yRgCGYQnwmdl0R3GB',
            '112200303',
            'VERIFICATION_IN_PROGRESS'
        )
            ->bankName('Bank Name')
            ->debitMandateReferenceId('debit_mandate_reference_id0')
            ->fingerprint('fingerprint0')
            ->locationId('S8GWD5example')
            ->referenceId('reference_id2')
            ->version(5)
            ->build()
    )
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
    ->build();
```

