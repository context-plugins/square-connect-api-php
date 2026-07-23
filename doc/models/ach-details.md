
# ACH Details

ACH-specific details about `BANK_ACCOUNT` type payments with the `transfer_type` of `ACH`.

## Structure

`ACHDetails`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountNumberSuffix` | `?string` | Optional | The last few digits of the bank account number.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `4` | getAccountNumberSuffix(): ?string | setAccountNumberSuffix(?string accountNumberSuffix): void |
| `accountType` | `?string` | Optional | The type of the bank account performing the transfer. The account type can be `CHECKING`,<br>`SAVINGS`, or `UNKNOWN`.<br><br>**Constraints**: *Maximum Length*: `50` | getAccountType(): ?string | setAccountType(?string accountType): void |
| `routingNumber` | `?string` | Optional | The routing number for the bank account.<br><br>**Constraints**: *Maximum Length*: `50` | getRoutingNumber(): ?string | setRoutingNumber(?string routingNumber): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\ACHDetailsBuilder;

$aCHDetails = ACHDetailsBuilder::init()
    ->accountNumberSuffix('account_number_suffix6')
    ->accountType('account_type2')
    ->routingNumber('routing_number6')
    ->build();
```

