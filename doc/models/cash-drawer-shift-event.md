
# Cash Drawer Shift Event

## Structure

`CashDrawerShiftEvent`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `createdAt` | `?string` | Optional | The event time in ISO 8601 format. | getCreatedAt(): ?string | setCreatedAt(?string createdAt): void |
| `description` | `?string` | Optional | An optional description of the event, entered by the employee that<br>created the event. | getDescription(): ?string | setDescription(?string description): void |
| `employeeId` | `?string` | Optional | The ID of the employee that created the event. | getEmployeeId(): ?string | setEmployeeId(?string employeeId): void |
| `eventMoney` | [`?Money`](../../doc/models/money.md) | Optional | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getEventMoney(): ?Money | setEventMoney(?Money eventMoney): void |
| `eventType` | `?string` | Optional | The type of cash drawer shift event. | getEventType(): ?string | setEventType(?string eventType): void |
| `id` | `?string` | Optional | The unique ID of the event. | getId(): ?string | setId(?string id): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CashDrawerShiftEventBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;

$cashDrawerShiftEvent = CashDrawerShiftEventBuilder::init()
    ->createdAt('created_at6')
    ->description('description4')
    ->employeeId('employee_id4')
    ->eventMoney(
        MoneyBuilder::init()
            ->amount(148)
            ->currency('currency2')
            ->build()
    )
    ->eventType('event_type4')
    ->build();
```

