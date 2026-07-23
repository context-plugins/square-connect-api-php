
# Customer Sort

Specifies how searched customers profiles are sorted, including the sort key and sort order.

## Structure

`CustomerSort`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `field` | `?string` | Optional | Use one or more customer attributes as the sort key to sort searched customer profiles.<br>For example, use the creation date (`created_at`) of customers or default attributes as the sort key.<br><br>Default: `DEFAULT`. | getField(): ?string | setField(?string field): void |
| `order` | `?string` | Optional | Indicates the order in which results should be sorted based on the<br>sort field value. Strings use standard alphabetic comparison<br>to determine order. Strings representing numbers are sorted as strings.<br><br>Default: `ASC`. | getOrder(): ?string | setOrder(?string order): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CustomerSortBuilder;

$customerSort = CustomerSortBuilder::init()
    ->field('field8')
    ->order('order8')
    ->build();
```

