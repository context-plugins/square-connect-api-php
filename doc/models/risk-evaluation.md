
# Risk Evaluation

Represents fraud risk information for the associated payment.

When you take a payment through Square's Payments API (using the `CreatePayment`
endpoint), Square evaluates it and assigns a risk level to the payment. Sellers
can use this information to determine the course of action (for example,
provide the goods/services or refund the payment).

## Structure

`RiskEvaluation`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `createdAt` | `?string` | Optional | The timestamp when payment risk was evaluated, in RFC 3339 format. | getCreatedAt(): ?string | setCreatedAt(?string createdAt): void |
| `riskLevel` | `?string` | Optional | The risk level associated with the payment | getRiskLevel(): ?string | setRiskLevel(?string riskLevel): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\RiskEvaluationBuilder;

$riskEvaluation = RiskEvaluationBuilder::init()
    ->createdAt('created_at6')
    ->riskLevel('risk_level2')
    ->build();
```

