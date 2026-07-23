
# Bank Account

Represents a bank account. For more information about
linking a bank account to a Square account, see
[Bank Accounts API](https://developer.squareup.com/docs/bank-accounts-api).

## Structure

`BankAccount`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountNumberSuffix` | `string` | Required | The last few digits of the account number.<br><br>**Constraints**: *Minimum Length*: `1` | getAccountNumberSuffix(): string | setAccountNumberSuffix(string accountNumberSuffix): void |
| `accountType` | `string` | Required | The financial purpose of the associated bank account. | getAccountType(): string | setAccountType(string accountType): void |
| `bankName` | `?string` | Optional | Read only. Name of actual financial institution.<br>For example "Bank of America".<br><br>**Constraints**: *Maximum Length*: `100` | getBankName(): ?string | setBankName(?string bankName): void |
| `country` | `string` | Required | The ISO 3166 Alpha-2 country code where the bank account is based. | getCountry(): string | setCountry(string country): void |
| `creditable` | `bool` | Required | Indicates whether it is possible for Square to send money to this bank account. | getCreditable(): bool | setCreditable(bool creditable): void |
| `currency` | `string` | Required | The 3-character ISO 4217 currency code indicating the operating<br>currency of the bank account. For example, the currency code for US dollars<br>is `USD`. | getCurrency(): string | setCurrency(string currency): void |
| `debitMandateReferenceId` | `?string` | Optional | Reference identifier that will be displayed to UK bank account owners<br>when collecting direct debit authorization. Only required for UK bank accounts. | getDebitMandateReferenceId(): ?string | setDebitMandateReferenceId(?string debitMandateReferenceId): void |
| `debitable` | `bool` | Required | Indicates whether it is possible for Square to take money from this<br>bank account. | getDebitable(): bool | setDebitable(bool debitable): void |
| `fingerprint` | `?string` | Optional | A Square-assigned, unique identifier for the bank account based on the<br>account information. The account fingerprint can be used to compare account<br>entries and determine if the they represent the same real-world bank account. | getFingerprint(): ?string | setFingerprint(?string fingerprint): void |
| `holderName` | `string` | Required | Name of the account holder. This name must match the name<br>on the targeted bank account record.<br><br>**Constraints**: *Minimum Length*: `1` | getHolderName(): string | setHolderName(string holderName): void |
| `id` | `string` | Required | The unique, Square-issued identifier for the bank account.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `30` | getId(): string | setId(string id): void |
| `locationId` | `?string` | Optional | The location to which the bank account belongs. | getLocationId(): ?string | setLocationId(?string locationId): void |
| `primaryBankIdentificationNumber` | `string` | Required | Primary identifier for the bank. For more information, see<br>[Bank Accounts API](https://developer.squareup.com/docs/bank-accounts-api).<br><br>**Constraints**: *Maximum Length*: `40` | getPrimaryBankIdentificationNumber(): string | setPrimaryBankIdentificationNumber(string primaryBankIdentificationNumber): void |
| `referenceId` | `?string` | Optional | Client-provided identifier for linking the banking account to an entity<br>in a third-party system (for example, a bank account number or a user identifier). | getReferenceId(): ?string | setReferenceId(?string referenceId): void |
| `secondaryBankIdentificationNumber` | `?string` | Optional | Secondary identifier for the bank. For more information, see<br>[Bank Accounts API](https://developer.squareup.com/docs/bank-accounts-api).<br><br>**Constraints**: *Maximum Length*: `40` | getSecondaryBankIdentificationNumber(): ?string | setSecondaryBankIdentificationNumber(?string secondaryBankIdentificationNumber): void |
| `status` | `string` | Required | Read-only. The current verification status of this BankAccount object. | getStatus(): string | setStatus(string status): void |
| `version` | `?int` | Optional | The current version of the `BankAccount`. | getVersion(): ?int | setVersion(?int version): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\BankAccountBuilder;

$bankAccount = BankAccountBuilder::init(
    'account_number_suffix0',
    'account_type6',
    'country2',
    false,
    'currency8',
    false,
    'holder_name4',
    'id8',
    'primary_bank_identification_number6',
    'status0'
)
    ->bankName('bank_name6')
    ->debitMandateReferenceId('debit_mandate_reference_id6')
    ->fingerprint('fingerprint4')
    ->locationId('location_id2')
    ->referenceId('reference_id4')
    ->build();
```

