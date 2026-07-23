
# Gift Card Status Enum

Indicates the gift card state.

## Enumeration

`GiftCardStatusEnum`

## Fields

| Name | Description |
|  --- | --- |
| `ACTIVE` | The gift card is active and can be used as a payment source. |
| `DEACTIVATED` | Any activity that changes the gift card balance is permanently forbidden. |
| `BLOCKED` | Any activity that changes the gift card balance is temporarily forbidden. |
| `PENDING` | The gift card is pending activation.<br>This is the state when a gift card is initially created. You must activate the gift card<br>before you can use it. |

## Example

```php
use SquareConnectAPILib\Models\GiftCardStatusEnum;

$giftCardStatus = GiftCardStatusEnum::ACTIVE;
```

