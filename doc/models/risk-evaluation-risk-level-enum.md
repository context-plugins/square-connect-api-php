
# Risk Evaluation Risk Level Enum

## Enumeration

`RiskEvaluationRiskLevelEnum`

## Fields

| Name | Description |
|  --- | --- |
| `PENDING` | Indicates Square is still evaluating the payment. |
| `NORMAL` | Indicates payment risk is within the normal range. |
| `MODERATE` | Indicates elevated risk level associated with the payment. |
| `HIGH` | Indicates significantly elevated risk level with the payment. |

## Example

```php
use SquareConnectAPILib\Models\RiskEvaluationRiskLevelEnum;

$riskEvaluationRiskLevel = RiskEvaluationRiskLevelEnum::MODERATE;
```

