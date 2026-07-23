
# Unlink Customer from Gift Card Request

A request to unlink a customer to a gift card

## Structure

`UnlinkCustomerFromGiftCardRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `customerId` | `string` | Required | **Constraints**: *Minimum Length*: `1`, *Maximum Length*: `191` | getCustomerId(): string | setCustomerId(string customerId): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\UnlinkCustomerFromGiftCardRequestBuilder;

$unlinkCustomerFromGiftCardRequest = UnlinkCustomerFromGiftCardRequestBuilder::init(
    'customer_id0'
)->build();
```

