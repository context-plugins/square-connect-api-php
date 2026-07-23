
# Transaction Product Enum

Indicates the Square product used to process a transaction.

## Enumeration

`TransactionProductEnum`

## Fields

| Name | Description |
|  --- | --- |
| `REGISTER` | Square Point of Sale. |
| `EXTERNAL_API` | The Square Connect API. |
| `BILLING` | A Square subscription for one of multiple products. |
| `APPOINTMENTS` | Square Appointments. |
| `INVOICES` | Square Invoices. |
| `ONLINE_STORE` | Square Online Store. |
| `PAYROLL` | Square Payroll. |
| `OTHER` | A Square product that does not match any other value. |

## Example

```php
use SquareConnectAPILib\Models\TransactionProductEnum;

$transactionProduct = TransactionProductEnum::PAYROLL;
```

