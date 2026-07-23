
# Link Customer to Gift Card Request

A request to link a customer to a gift card

## Structure

`LinkCustomerToGiftCardRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `customerId` | `string` | Required | The ID of the customer to be linked.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `191` | getCustomerId(): string | setCustomerId(string customerId): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\LinkCustomerToGiftCardRequestBuilder;

$linkCustomerToGiftCardRequest = LinkCustomerToGiftCardRequestBuilder::init(
    'customer_id4'
)->build();
```

