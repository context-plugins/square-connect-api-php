
# Sort Order Enum

The order (e.g., chronological or alphabetical) in which results from a request are returned.

## Enumeration

`SortOrderEnum`

## Fields

| Name | Description |
|  --- | --- |
| `DESC` | The results are returned in descending (e.g., newest-first or Z-A) order. |
| `ASC` | The results are returned in ascending (e.g., oldest-first or A-Z) order. |

## Example

```php
use SquareConnectAPILib\Models\SortOrderEnum;

$sortOrder = SortOrderEnum::DESC;
```

