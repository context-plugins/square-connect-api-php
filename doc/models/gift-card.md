
# Gift Card

Represents a Square gift card.

## Structure

`GiftCard`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `balanceMoney` | [`?Money`](../../doc/models/money.md) | Optional | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getBalanceMoney(): ?Money | setBalanceMoney(?Money balanceMoney): void |
| `createdAt` | `?string` | Optional | The timestamp when the gift card was created, in RFC 3339 format.<br>In the case of a digital gift card, it is the time when you create a card<br>(using the Square Point of Sale application, Seller Dashboard, or Gift Cards API).  <br>In the case of a plastic gift card, it is the time when Square associates the card with the<br>seller at the time of activation. | getCreatedAt(): ?string | setCreatedAt(?string createdAt): void |
| `customerIds` | `?(string[])` | Optional | The IDs of the customers to whom this gift card is linked.<br><br>**Constraints**: *Maximum Length*: `191` | getCustomerIds(): ?array | setCustomerIds(?array customerIds): void |
| `gan` | `?string` | Optional | The gift card account number. | getGan(): ?string | setGan(?string gan): void |
| `ganSource` | `?array` | Optional | - | getGanSource(): ?array | setGanSource(?array ganSource): void |
| `id` | `?string` | Optional | The Square-assigned ID of the gift card. | getId(): ?string | setId(?string id): void |
| `state` | `?array` | Optional | - | getState(): ?array | setState(?array state): void |
| `type` | `array` | Required | - | getType(): array | setType(array type): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\GiftCardBuilder;
use SquareConnectAPILib\ApiHelper;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;

$giftCard = GiftCardBuilder::init(
    ApiHelper::deserialize('{"key1":"val1","key2":"val2"}')
)
    ->balanceMoney(
        MoneyBuilder::init()
            ->amount(146)
            ->currency('currency6')
            ->build()
    )
    ->createdAt('created_at0')
    ->customerIds(
        [
            'customer_ids9'
        ]
    )
    ->gan('gan8')
    ->ganSource(ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

