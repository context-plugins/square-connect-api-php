
# Order Return Service Charge

Represents the service charge applied to the original order.

## Structure

`OrderReturnServiceCharge`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amountMoney` | [`?Money`](../../doc/models/money.md) | Optional | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getAmountMoney(): ?Money | setAmountMoney(?Money amountMoney): void |
| `appliedMoney` | [`?Money`](../../doc/models/money.md) | Optional | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getAppliedMoney(): ?Money | setAppliedMoney(?Money appliedMoney): void |
| `appliedTaxes` | [`?(OrderLineItemAppliedTax[])`](../../doc/models/order-line-item-applied-tax.md) | Optional | The list of references to `OrderReturnTax` entities applied to the<br>`OrderReturnServiceCharge`. Each `OrderLineItemAppliedTax` has a `tax_uid`<br>that references the `uid` of a top-level `OrderReturnTax` that is being<br>applied to the `OrderReturnServiceCharge`. On reads, the applied amount is<br>populated. | getAppliedTaxes(): ?array | setAppliedTaxes(?array appliedTaxes): void |
| `calculationPhase` | `?string` | Optional | The calculation phase after which to apply the service charge. | getCalculationPhase(): ?string | setCalculationPhase(?string calculationPhase): void |
| `catalogObjectId` | `?string` | Optional | The catalog object ID of the associated [OrderServiceCharge](https://developer.squareup.com/reference/square_2021-08-18/objects/OrderServiceCharge).<br><br>**Constraints**: *Maximum Length*: `192` | getCatalogObjectId(): ?string | setCatalogObjectId(?string catalogObjectId): void |
| `catalogVersion` | `?int` | Optional | The version of the catalog object that this service charge references. | getCatalogVersion(): ?int | setCatalogVersion(?int catalogVersion): void |
| `name` | `?string` | Optional | The name of the service charge.<br><br>**Constraints**: *Maximum Length*: `255` | getName(): ?string | setName(?string name): void |
| `percentage` | `?string` | Optional | The percentage of the service charge, as a string representation of<br>a decimal number. For example, a value of `"7.25"` corresponds to a<br>percentage of 7.25%.<br><br>Either `percentage` or `amount_money` should be set, but not both.<br><br>**Constraints**: *Maximum Length*: `10` | getPercentage(): ?string | setPercentage(?string percentage): void |
| `sourceServiceChargeUid` | `?string` | Optional | The service charge `uid` from the order containing the original<br>service charge. `source_service_charge_uid` is `null` for<br>unlinked returns.<br><br>**Constraints**: *Maximum Length*: `60` | getSourceServiceChargeUid(): ?string | setSourceServiceChargeUid(?string sourceServiceChargeUid): void |
| `taxable` | `?bool` | Optional | Indicates whether the surcharge can be taxed. Service charges<br>calculated in the `TOTAL_PHASE` cannot be marked as taxable. | getTaxable(): ?bool | setTaxable(?bool taxable): void |
| `totalMoney` | [`?Money`](../../doc/models/money.md) | Optional | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getTotalMoney(): ?Money | setTotalMoney(?Money totalMoney): void |
| `totalTaxMoney` | [`?Money`](../../doc/models/money.md) | Optional | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getTotalTaxMoney(): ?Money | setTotalTaxMoney(?Money totalTaxMoney): void |
| `uid` | `?string` | Optional | A unique ID that identifies the return service charge only within this order.<br><br>**Constraints**: *Maximum Length*: `60` | getUid(): ?string | setUid(?string uid): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\OrderReturnServiceChargeBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;
use SquareConnectAPILib\Models\Builders\OrderLineItemAppliedTaxBuilder;

$orderReturnServiceCharge = OrderReturnServiceChargeBuilder::init()
    ->amountMoney(
        MoneyBuilder::init()
            ->amount(186)
            ->currency('currency8')
            ->build()
    )
    ->appliedMoney(
        MoneyBuilder::init()
            ->amount(196)
            ->currency('currency8')
            ->build()
    )
    ->appliedTaxes(
        [
            OrderLineItemAppliedTaxBuilder::init(
                'tax_uid4'
            )
                ->appliedMoney(
                    MoneyBuilder::init()
                        ->amount(196)
                        ->currency('currency8')
                        ->build()
                )
                ->uid('uid0')
                ->build(),
            OrderLineItemAppliedTaxBuilder::init(
                'tax_uid4'
            )
                ->appliedMoney(
                    MoneyBuilder::init()
                        ->amount(196)
                        ->currency('currency8')
                        ->build()
                )
                ->uid('uid0')
                ->build(),
            OrderLineItemAppliedTaxBuilder::init(
                'tax_uid4'
            )
                ->appliedMoney(
                    MoneyBuilder::init()
                        ->amount(196)
                        ->currency('currency8')
                        ->build()
                )
                ->uid('uid0')
                ->build()
        ]
    )
    ->calculationPhase('calculation_phase4')
    ->catalogObjectId('catalog_object_id8')
    ->build();
```

