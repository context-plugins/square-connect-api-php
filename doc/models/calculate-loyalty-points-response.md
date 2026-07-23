
# Calculate Loyalty Points Response

A response that includes the points that the buyer can earn from
a specified purchase.

## Structure

`CalculateLoyaltyPointsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `points` | `?int` | Optional | The points that the buyer can earn from a specified purchase.<br><br>**Constraints**: `>= 0` | getPoints(): ?int | setPoints(?int points): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CalculateLoyaltyPointsResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;

$calculateLoyaltyPointsResponse = CalculateLoyaltyPointsResponseBuilder::init()
    ->errors(
        [
            ErrorBuilder::init(
                'category8',
                'code8'
            )
                ->detail('detail6')
                ->field('field4')
                ->build(),
            ErrorBuilder::init(
                'category8',
                'code8'
            )
                ->detail('detail6')
                ->field('field4')
                ->build(),
            ErrorBuilder::init(
                'category8',
                'code8'
            )
                ->detail('detail6')
                ->field('field4')
                ->build()
        ]
    )
    ->points(6)
    ->build();
```

