
# Terminal Refund

## Structure

`TerminalRefund`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amountMoney` | [`Money`](../../doc/models/money.md) | Required | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getAmountMoney(): Money | setAmountMoney(Money amountMoney): void |
| `appId` | `?string` | Optional | The ID of the application that created the refund. | getAppId(): ?string | setAppId(?string appId): void |
| `cancelReason` | `?string` | Optional | Present if the status is `CANCELED`. | getCancelReason(): ?string | setCancelReason(?string cancelReason): void |
| `createdAt` | `?string` | Optional | The time when the `TerminalRefund` was created, as an RFC 3339 timestamp. | getCreatedAt(): ?string | setCreatedAt(?string createdAt): void |
| `deadlineDuration` | `?string` | Optional | The RFC 3339 duration, after which the refund is automatically canceled.<br>A `TerminalRefund` that is `PENDING` is automatically `CANCELED` and has a cancellation reason<br>of `TIMED_OUT`.<br><br>Default: 5 minutes from creation.<br><br>Maximum: 5 minutes | getDeadlineDuration(): ?string | setDeadlineDuration(?string deadlineDuration): void |
| `deviceId` | `?string` | Optional | The unique ID of the device intended for this `TerminalRefund`.<br>The Id can be retrieved from /v2/devices api. | getDeviceId(): ?string | setDeviceId(?string deviceId): void |
| `id` | `?string` | Optional | A unique ID for this `TerminalRefund`.<br><br>**Constraints**: *Minimum Length*: `10`, *Maximum Length*: `255` | getId(): ?string | setId(?string id): void |
| `locationId` | `?string` | Optional | The location of the device where the `TerminalRefund` was directed. | getLocationId(): ?string | setLocationId(?string locationId): void |
| `orderId` | `?string` | Optional | The reference to the Square order ID for the payment identified by the `payment_id`. | getOrderId(): ?string | setOrderId(?string orderId): void |
| `paymentId` | `string` | Required | The unique ID of the payment being refunded.<br><br>**Constraints**: *Minimum Length*: `1` | getPaymentId(): string | setPaymentId(string paymentId): void |
| `reason` | `?string` | Optional | A description of the reason for the refund.<br>Note: maximum 192 characters<br><br>**Constraints**: *Maximum Length*: `192` | getReason(): ?string | setReason(?string reason): void |
| `refundId` | `?string` | Optional | The reference to the payment refund created by completing this `TerminalRefund`. | getRefundId(): ?string | setRefundId(?string refundId): void |
| `status` | `?string` | Optional | The status of the `TerminalRefund`.<br>Options: `PENDING`, `IN_PROGRESS`, `CANCELED`, or `COMPLETED`. | getStatus(): ?string | setStatus(?string status): void |
| `updatedAt` | `?string` | Optional | The time when the `TerminalRefund` was last updated, as an RFC 3339 timestamp. | getUpdatedAt(): ?string | setUpdatedAt(?string updatedAt): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\TerminalRefundBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;

$terminalRefund = TerminalRefundBuilder::init(
    MoneyBuilder::init()
        ->amount(186)
        ->currency('currency8')
        ->build(),
    'payment_id2'
)
    ->appId('app_id4')
    ->cancelReason('cancel_reason8')
    ->createdAt('created_at0')
    ->deadlineDuration('deadline_duration6')
    ->deviceId('device_id8')
    ->build();
```

