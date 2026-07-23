
# Range

The range of a number value between the specified lower and upper bounds.

## Structure

`Range`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `max` | `?string` | Optional | The upper bound of the number range. | getMax(): ?string | setMax(?string max): void |
| `min` | `?string` | Optional | The lower bound of the number range. | getMin(): ?string | setMin(?string min): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\RangeBuilder;

$range = RangeBuilder::init()
    ->max('max8')
    ->min('min6')
    ->build();
```

