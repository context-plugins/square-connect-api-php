
# Date Range

A range defined by two dates. Used for filtering a query for Connect v2
objects that have date properties.

## Structure

`DateRange`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `endDate` | `?string` | Optional | A string in `YYYY-MM-DD` format, such as `2017-10-31`, per the ISO 8601<br>extended format for calendar dates.<br>The end of a date range (inclusive). | getEndDate(): ?string | setEndDate(?string endDate): void |
| `startDate` | `?string` | Optional | A string in `YYYY-MM-DD` format, such as `2017-10-31`, per the ISO 8601<br>extended format for calendar dates.<br>The beginning of a date range (inclusive). | getStartDate(): ?string | setStartDate(?string startDate): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\DateRangeBuilder;

$dateRange = DateRangeBuilder::init()
    ->endDate('end_date4')
    ->startDate('start_date2')
    ->build();
```

