
# V1 Phone Number

Represents a phone number.

## Structure

`V1PhoneNumber`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `callingCode` | `string` | Required | The phone number's international calling code. For US phone numbers, this value is +1. | getCallingCode(): string | setCallingCode(string callingCode): void |
| `number` | `string` | Required | The phone number. | getNumber(): string | setNumber(string number): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\V1PhoneNumberBuilder;

$v1PhoneNumber = V1PhoneNumberBuilder::init(
    'calling_code0',
    'number4'
)->build();
```

