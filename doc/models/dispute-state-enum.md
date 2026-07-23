
# Dispute State Enum

The list of possible dispute states.

## Enumeration

`DisputeStateEnum`

## Fields

| Name |
|  --- |
| `UNKNOWN_STATE` |
| `INQUIRY_EVIDENCE_REQUIRED` |
| `INQUIRY_PROCESSING` |
| `INQUIRY_CLOSED` |
| `EVIDENCE_REQUIRED` |
| `PROCESSING` |
| `WON` |
| `LOST` |
| `ACCEPTED` |
| `WAITING_THIRD_PARTY` |

## Example

```php
use SquareConnectAPILib\Models\DisputeStateEnum;

$disputeState = DisputeStateEnum::WON;
```

