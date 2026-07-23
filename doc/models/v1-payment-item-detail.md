
# V1 Payment Item Detail

V1PaymentItemDetail

## Structure

`V1PaymentItemDetail`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `categoryName` | `?string` | Optional | The name of the item's merchant-defined category, if any. | getCategoryName(): ?string | setCategoryName(?string categoryName): void |
| `itemId` | `?string` | Optional | The unique ID of the item purchased, if any. | getItemId(): ?string | setItemId(?string itemId): void |
| `itemVariationId` | `?string` | Optional | The unique ID of the item variation purchased, if any. | getItemVariationId(): ?string | setItemVariationId(?string itemVariationId): void |
| `sku` | `?string` | Optional | The item's merchant-defined SKU, if any. | getSku(): ?string | setSku(?string sku): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\V1PaymentItemDetailBuilder;

$v1PaymentItemDetail = V1PaymentItemDetailBuilder::init()
    ->categoryName('category_name4')
    ->itemId('item_id4')
    ->itemVariationId('item_variation_id8')
    ->sku('sku0')
    ->build();
```

