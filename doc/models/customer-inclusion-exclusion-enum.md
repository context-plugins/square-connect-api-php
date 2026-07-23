
# Customer Inclusion Exclusion Enum

Indicates whether customers should be included in, or excluded from,
the result set when they match the filtering criteria.

## Enumeration

`CustomerInclusionExclusionEnum`

## Fields

| Name | Description |
|  --- | --- |
| `INCLUDE_` | Customers should be included in the result set when they match the<br>filtering criteria. |
| `EXCLUDE` | Customers should be excluded from the result set when they match<br>the filtering criteria. |

## Example

```php
use SquareConnectAPILib\Models\CustomerInclusionExclusionEnum;

$customerInclusionExclusion = CustomerInclusionExclusionEnum::INCLUDE_;
```

