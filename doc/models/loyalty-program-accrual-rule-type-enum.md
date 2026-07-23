
# Loyalty Program Accrual Rule Type Enum

The type of the accrual rule that defines how buyers can earn points.

## Enumeration

`LoyaltyProgramAccrualRuleTypeEnum`

## Fields

| Name | Description |
|  --- | --- |
| `VISIT` | A visit-based accrual rule. A buyer earns points for each visit.<br>You can specify the minimum purchase required. |
| `SPEND` | A spend-based accrual rule. A buyer earns points based on the amount<br>spent. |
| `ITEM_VARIATION` | An accrual rule based on an item variation. For example, accrue<br>points for purchasing a coffee. |
| `CATEGORY` | An accrual rule based on an item category. For example, accrue points<br>for purchasing any item in the "hot drink" category: coffee, tea, or hot cocoa. |

## Example

```php
use SquareConnectAPILib\Models\LoyaltyProgramAccrualRuleTypeEnum;

$loyaltyProgramAccrualRuleType = LoyaltyProgramAccrualRuleTypeEnum::ITEM_VARIATION;
```

