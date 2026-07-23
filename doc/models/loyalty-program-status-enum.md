
# Loyalty Program Status Enum

Indicates whether the program is currently active.

## Enumeration

`LoyaltyProgramStatusEnum`

## Fields

| Name | Description |
|  --- | --- |
| `INACTIVE` | The loyalty program does not have an active subscription.<br>Loyalty API requests fail. |
| `ACTIVE` | The program is fully functional. The program has an active subscription. |

## Example

```php
use SquareConnectAPILib\Models\LoyaltyProgramStatusEnum;

$loyaltyProgramStatus = LoyaltyProgramStatusEnum::INACTIVE;
```

