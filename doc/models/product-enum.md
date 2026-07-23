
# Product Enum

Indicates the Square product used to generate an inventory change.

## Enumeration

`ProductEnum`

## Fields

| Name | Description |
|  --- | --- |
| `SQUARE_POS` | Square Point of Sale application. |
| `EXTERNAL_API` | Square Connect APIs (Transactions API, Checkout API). |
| `BILLING` | A Square subscription (various products). |
| `APPOINTMENTS` | Square Appointments. |
| `INVOICES` | Square Invoices. |
| `ONLINE_STORE` | Square Online Store. |
| `PAYROLL` | Square Payroll. |
| `DASHBOARD` | Square Dashboard |
| `ITEM_LIBRARY_IMPORT` | Item Library Import |
| `OTHER` | A Square product that does not match any other value. |

## Example

```php
use SquareConnectAPILib\Models\ProductEnum;

$product = ProductEnum::SQUARE_POS;
```

