
# Bank Account Payment Details

Additional details about BANK_ACCOUNT type payments.

## Structure

`BankAccountPaymentDetails`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountOwnershipType` | `?string` | Optional | The ownership type of the bank account performing the transfer.<br>The type can be `INDIVIDUAL`, `COMPANY`, or `UNKNOWN`.<br><br>**Constraints**: *Maximum Length*: `50` | getAccountOwnershipType(): ?string | setAccountOwnershipType(?string accountOwnershipType): void |
| `achDetails` | [`?ACHDetails`](../../doc/models/ach-details.md) | Optional | ACH-specific details about `BANK_ACCOUNT` type payments with the `transfer_type` of `ACH`. | getAchDetails(): ?ACHDetails | setAchDetails(?ACHDetails achDetails): void |
| `bankName` | `?string` | Optional | The name of the bank associated with the bank account.<br><br>**Constraints**: *Maximum Length*: `100` | getBankName(): ?string | setBankName(?string bankName): void |
| `country` | `?string` | Optional | The two-letter ISO code representing the country the bank account is located in.<br><br>**Constraints**: *Minimum Length*: `2`, *Maximum Length*: `2` | getCountry(): ?string | setCountry(?string country): void |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Information about errors encountered during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `fingerprint` | `?string` | Optional | Uniquely identifies the bank account for this seller and can be used<br>to determine if payments are from the same bank account.<br><br>**Constraints**: *Maximum Length*: `255` | getFingerprint(): ?string | setFingerprint(?string fingerprint): void |
| `statementDescription` | `?string` | Optional | The statement description as sent to the bank.<br><br>**Constraints**: *Maximum Length*: `1000` | getStatementDescription(): ?string | setStatementDescription(?string statementDescription): void |
| `transferType` | `?string` | Optional | The type of the bank transfer. The type can be `ACH` or `UNKNOWN`.<br><br>**Constraints**: *Maximum Length*: `50` | getTransferType(): ?string | setTransferType(?string transferType): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\BankAccountPaymentDetailsBuilder;
use SquareConnectAPILib\Models\Builders\ACHDetailsBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;

$bankAccountPaymentDetails = BankAccountPaymentDetailsBuilder::init()
    ->accountOwnershipType('account_ownership_type4')
    ->achDetails(
        ACHDetailsBuilder::init()
            ->accountNumberSuffix('account_number_suffix2')
            ->accountType('account_type2')
            ->routingNumber('routing_number0')
            ->build()
    )
    ->bankName('bank_name0')
    ->country('country8')
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

