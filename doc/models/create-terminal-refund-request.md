
# Create Terminal Refund Request

## Structure

`CreateTerminalRefundRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `idempotencyKey` | `string` | Required | A unique string that identifies this `CreateRefund` request. Keys can be any valid string but<br>must be unique for every `CreateRefund` request.<br><br>See [Idempotency keys](https://developer.squareup.com/docs/basics/api101/idempotency) for more information.<br><br>**Constraints**: *Minimum Length*: `1` | getIdempotencyKey(): string | setIdempotencyKey(string idempotencyKey): void |
| `refund` | [`?TerminalRefund`](../../doc/models/terminal-refund.md) | Optional | - | getRefund(): ?TerminalRefund | setRefund(?TerminalRefund refund): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CreateTerminalRefundRequestBuilder;
use SquareConnectAPILib\Models\Builders\TerminalRefundBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;

$createTerminalRefundRequest = CreateTerminalRefundRequestBuilder::init(
    'idempotency_key0'
)
    ->refund(
        TerminalRefundBuilder::init(
            MoneyBuilder::init()
                ->amount(186)
                ->currency('currency8')
                ->build(),
            'payment_id8'
        )
            ->appId('app_id8')
            ->cancelReason('cancel_reason4')
            ->createdAt('created_at6')
            ->deadlineDuration('deadline_duration0')
            ->deviceId('device_id4')
            ->build()
    )
    ->build();
```

