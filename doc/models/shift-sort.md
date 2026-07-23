
# Shift Sort

Sets the sort order of search results.

## Structure

`ShiftSort`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `field` | `?string` | Optional | The field to sort on. | getField(): ?string | setField(?string field): void |
| `order` | `?string` | Optional | The order in which results are returned. Defaults to DESC. | getOrder(): ?string | setOrder(?string order): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\ShiftSortBuilder;

$shiftSort = ShiftSortBuilder::init()
    ->field('field0')
    ->order('order0')
    ->build();
```

