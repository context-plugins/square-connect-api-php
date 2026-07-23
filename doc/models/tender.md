
# Tender

Represents a tender (i.e., a method of payment) used in a Square transaction.

## Structure

`Tender`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `additionalRecipients` | [`?(AdditionalRecipient[])`](../../doc/models/additional-recipient.md) | Optional | Additional recipients (other than the merchant) receiving a portion of this tender.<br>For example, fees assessed on the purchase by a third party integration. | getAdditionalRecipients(): ?array | setAdditionalRecipients(?array additionalRecipients): void |
| `amountMoney` | [`?Money`](../../doc/models/money.md) | Optional | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getAmountMoney(): ?Money | setAmountMoney(?Money amountMoney): void |
| `cardDetails` | [`?TenderCardDetails`](../../doc/models/tender-card-details.md) | Optional | Represents additional details of a tender with `type` `CARD` or `SQUARE_GIFT_CARD` | getCardDetails(): ?TenderCardDetails | setCardDetails(?TenderCardDetails cardDetails): void |
| `cashDetails` | [`?TenderCashDetails`](../../doc/models/tender-cash-details.md) | Optional | Represents the details of a tender with `type` `CASH`. | getCashDetails(): ?TenderCashDetails | setCashDetails(?TenderCashDetails cashDetails): void |
| `createdAt` | `?string` | Optional | The timestamp for when the tender was created, in RFC 3339 format.<br><br>**Constraints**: *Maximum Length*: `32` | getCreatedAt(): ?string | setCreatedAt(?string createdAt): void |
| `customerId` | `?string` | Optional | If the tender is associated with a customer or represents a customer's card on file,<br>this is the ID of the associated customer.<br><br>**Constraints**: *Maximum Length*: `191` | getCustomerId(): ?string | setCustomerId(?string customerId): void |
| `id` | `?string` | Optional | The tender's unique ID.<br><br>**Constraints**: *Maximum Length*: `192` | getId(): ?string | setId(?string id): void |
| `locationId` | `?string` | Optional | The ID of the transaction's associated location.<br><br>**Constraints**: *Maximum Length*: `50` | getLocationId(): ?string | setLocationId(?string locationId): void |
| `note` | `?string` | Optional | An optional note associated with the tender at the time of payment.<br><br>**Constraints**: *Maximum Length*: `500` | getNote(): ?string | setNote(?string note): void |
| `paymentId` | `?string` | Optional | The ID of the [Payment](https://developer.squareup.com/reference/square_2021-08-18/objects/Payment) that corresponds to this tender.<br>This value is only present for payments created with the v2 Payments API.<br><br>**Constraints**: *Maximum Length*: `192` | getPaymentId(): ?string | setPaymentId(?string paymentId): void |
| `processingFeeMoney` | [`?Money`](../../doc/models/money.md) | Optional | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getProcessingFeeMoney(): ?Money | setProcessingFeeMoney(?Money processingFeeMoney): void |
| `tipMoney` | [`?Money`](../../doc/models/money.md) | Optional | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getTipMoney(): ?Money | setTipMoney(?Money tipMoney): void |
| `transactionId` | `?string` | Optional | The ID of the tender's associated transaction.<br><br>**Constraints**: *Maximum Length*: `192` | getTransactionId(): ?string | setTransactionId(?string transactionId): void |
| `type` | `string` | Required | The type of tender, such as `CARD` or `CASH`. | getType(): string | setType(string type): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\TenderBuilder;
use SquareConnectAPILib\Models\Builders\AdditionalRecipientBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;
use SquareConnectAPILib\Models\Builders\TenderCardDetailsBuilder;
use SquareConnectAPILib\Models\Builders\CardBuilder;
use SquareConnectAPILib\Models\Builders\AddressBuilder;
use SquareConnectAPILib\Models\Builders\TenderCashDetailsBuilder;

$tender = TenderBuilder::init(
    'type4'
)
    ->additionalRecipients(
        [
            AdditionalRecipientBuilder::init(
                MoneyBuilder::init()
                    ->amount(186)
                    ->currency('currency8')
                    ->build(),
                'location_id0'
            )
                ->description('description6')
                ->receivableId('receivable_id6')
                ->build(),
            AdditionalRecipientBuilder::init(
                MoneyBuilder::init()
                    ->amount(186)
                    ->currency('currency8')
                    ->build(),
                'location_id0'
            )
                ->description('description6')
                ->receivableId('receivable_id6')
                ->build(),
            AdditionalRecipientBuilder::init(
                MoneyBuilder::init()
                    ->amount(186)
                    ->currency('currency8')
                    ->build(),
                'location_id0'
            )
                ->description('description6')
                ->receivableId('receivable_id6')
                ->build()
        ]
    )
    ->amountMoney(
        MoneyBuilder::init()
            ->amount(186)
            ->currency('currency8')
            ->build()
    )
    ->cardDetails(
        TenderCardDetailsBuilder::init()
            ->card(
                CardBuilder::init()
                    ->billingAddress(
                        AddressBuilder::init()
                            ->addressLine1('address_line_12')
                            ->addressLine2('address_line_28')
                            ->addressLine3('address_line_34')
                            ->administrativeDistrictLevel1('administrative_district_level_12')
                            ->administrativeDistrictLevel2('administrative_district_level_26')
                            ->build()
                    )
                    ->bin('bin6')
                    ->cardBrand('card_brand0')
                    ->cardType('card_type8')
                    ->cardholderName('cardholder_name8')
                    ->build()
            )
            ->entryMethod('entry_method8')
            ->status('status4')
            ->build()
    )
    ->cashDetails(
        TenderCashDetailsBuilder::init()
            ->buyerTenderedMoney(
                MoneyBuilder::init()
                    ->amount(238)
                    ->currency('currency4')
                    ->build()
            )
            ->changeBackMoney(
                MoneyBuilder::init()
                    ->amount(78)
                    ->currency('currency6')
                    ->build()
            )
            ->build()
    )
    ->createdAt('created_at4')
    ->build();
```

