
# Terminal Refund Query Sort

## Structure

`TerminalRefundQuerySort`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `sortOrder` | `?string` | Optional | The order in which results are listed.<br><br>- `ASC` - Oldest to newest.<br>- `DESC` - Newest to oldest (default). | getSortOrder(): ?string | setSortOrder(?string sortOrder): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\TerminalRefundQuerySortBuilder;

$terminalRefundQuerySort = TerminalRefundQuerySortBuilder::init()
    ->sortOrder('sort_order2')
    ->build();
```

