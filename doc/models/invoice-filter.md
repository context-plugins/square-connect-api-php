
# Invoice Filter

Describes query filters to apply.

## Structure

`InvoiceFilter`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `customerIds` | `?(string[])` | Optional | Limits the search to the specified customers, within the specified locations.<br>Specifying a customer is optional. In the current implementation,<br>a maximum of one customer can be specified. | getCustomerIds(): ?array | setCustomerIds(?array customerIds): void |
| `locationIds` | `string[]` | Required | Limits the search to the specified locations. A location is required.<br>In the current implementation, only one location can be specified. | getLocationIds(): array | setLocationIds(array locationIds): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\InvoiceFilterBuilder;

$invoiceFilter = InvoiceFilterBuilder::init(
    [
        'location_ids8',
        'location_ids9'
    ]
)
    ->customerIds(
        [
            'customer_ids5'
        ]
    )
    ->build();
```

