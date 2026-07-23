
# V1 Order History Entry Action Enum

## Enumeration

`V1OrderHistoryEntryActionEnum`

## Fields

| Name |
|  --- |
| `ORDER_PLACED` |
| `DECLINED` |
| `PAYMENT_RECEIVED` |
| `CANCELED` |
| `COMPLETED` |
| `REFUNDED` |
| `EXPIRED` |

## Example

```php
use SquareConnectAPILib\Models\V1OrderHistoryEntryActionEnum;

$v1OrderHistoryEntryAction = V1OrderHistoryEntryActionEnum::DECLINED;
```

