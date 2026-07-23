
# Item Variation Location Overrides

Price and inventory alerting overrides for a `CatalogItemVariation` at a specific `Location`.

## Structure

`ItemVariationLocationOverrides`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `inventoryAlertThreshold` | `?int` | Optional | If the inventory quantity for the variation is less than or equal to this value and `inventory_alert_type`<br>is `LOW_QUANTITY`, the variation displays an alert in the merchant dashboard.<br><br>This value is always an integer. | getInventoryAlertThreshold(): ?int | setInventoryAlertThreshold(?int inventoryAlertThreshold): void |
| `inventoryAlertType` | `?string` | Optional | Indicates whether the `CatalogItemVariation` displays an alert when its inventory<br>quantity is less than or equal to its `inventory_alert_threshold`. | getInventoryAlertType(): ?string | setInventoryAlertType(?string inventoryAlertType): void |
| `locationId` | `?string` | Optional | The ID of the `Location`. This can include locations that are deactivated. | getLocationId(): ?string | setLocationId(?string locationId): void |
| `priceMoney` | [`?Money`](../../doc/models/money.md) | Optional | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getPriceMoney(): ?Money | setPriceMoney(?Money priceMoney): void |
| `pricingType` | `?string` | Optional | The pricing type (fixed or variable) for the `CatalogItemVariation` at the given `Location`. | getPricingType(): ?string | setPricingType(?string pricingType): void |
| `trackInventory` | `?bool` | Optional | If `true`, inventory tracking is active for the `CatalogItemVariation` at this `Location`. | getTrackInventory(): ?bool | setTrackInventory(?bool trackInventory): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\ItemVariationLocationOverridesBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;

$itemVariationLocationOverrides = ItemVariationLocationOverridesBuilder::init()
    ->inventoryAlertThreshold(196)
    ->inventoryAlertType('inventory_alert_type0')
    ->locationId('location_id2')
    ->priceMoney(
        MoneyBuilder::init()
            ->amount(202)
            ->currency('currency2')
            ->build()
    )
    ->pricingType('pricing_type4')
    ->build();
```

