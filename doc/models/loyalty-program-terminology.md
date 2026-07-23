
# Loyalty Program Terminology

Represents the naming used for loyalty points.

## Structure

`LoyaltyProgramTerminology`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `one` | `string` | Required | A singular unit for a point (for example, 1 point is called 1 star).<br><br>**Constraints**: *Minimum Length*: `1` | getOne(): string | setOne(string one): void |
| `other` | `string` | Required | A plural unit for point (for example, 10 points is called 10 stars).<br><br>**Constraints**: *Minimum Length*: `1` | getOther(): string | setOther(string other): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\LoyaltyProgramTerminologyBuilder;

$loyaltyProgramTerminology = LoyaltyProgramTerminologyBuilder::init(
    'one4',
    'other0'
)->build();
```

