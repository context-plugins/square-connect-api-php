
# Refund Status Enum

Indicates a refund's current status.

## Enumeration

`RefundStatusEnum`

## Fields

| Name | Description |
|  --- | --- |
| `PENDING` | The refund is pending. |
| `APPROVED` | The refund has been approved by Square. |
| `REJECTED` | The refund has been rejected by Square. |
| `FAILED` | The refund failed. |

## Example

```php
use SquareConnectAPILib\Models\RefundStatusEnum;

$refundStatus = RefundStatusEnum::REJECTED;
```

