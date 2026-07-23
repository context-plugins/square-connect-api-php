
# Customer Creation Source Filter

The creation source filter.

If one or more creation sources are set, customer profiles are included in,
or excluded from, the result if they match at least one of the filter criteria.

## Structure

`CustomerCreationSourceFilter`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `rule` | `?string` | Optional | Indicates whether a customer profile matching the filter criteria<br>should be included in the result or excluded from the result.<br><br>Default: `INCLUDE`. | getRule(): ?string | setRule(?string rule): void |
| `values` | `?(string[])` | Optional | The list of creation sources used as filtering criteria. | getValues(): ?array | setValues(?array values): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CustomerCreationSourceFilterBuilder;

$customerCreationSourceFilter = CustomerCreationSourceFilterBuilder::init()
    ->rule('rule0')
    ->values(
        [
            'values0'
        ]
    )
    ->build();
```

