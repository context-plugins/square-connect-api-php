
# Payment

Represents a payment processed by the Square API.

## Structure

`Payment`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amountMoney` | [`?Money`](../../doc/models/money.md) | Optional | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getAmountMoney(): ?Money | setAmountMoney(?Money amountMoney): void |
| `appFeeMoney` | [`?Money`](../../doc/models/money.md) | Optional | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getAppFeeMoney(): ?Money | setAppFeeMoney(?Money appFeeMoney): void |
| `approvedMoney` | [`?Money`](../../doc/models/money.md) | Optional | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getApprovedMoney(): ?Money | setApprovedMoney(?Money approvedMoney): void |
| `bankAccountDetails` | [`?BankAccountPaymentDetails`](../../doc/models/bank-account-payment-details.md) | Optional | Additional details about BANK_ACCOUNT type payments. | getBankAccountDetails(): ?BankAccountPaymentDetails | setBankAccountDetails(?BankAccountPaymentDetails bankAccountDetails): void |
| `billingAddress` | [`?Address`](../../doc/models/address.md) | Optional | Represents a postal address in a country. The address format is based<br>on an [open-source library from Google](https://github.com/google/libaddressinput). For more information,<br>see [AddressValidationMetadata](https://github.com/google/libaddressinput/wiki/AddressValidationMetadata).<br>This format has dedicated fields for four address components: postal code,<br>locality (city), administrative district (state, prefecture, or province), and<br>sublocality (town or village). These components have dedicated fields in the<br>`Address` object because software sometimes behaves differently based on them.<br>For example, sales tax software may charge different amounts of sales tax<br>based on the postal code, and some software is only available in<br>certain states due to compliance reasons.<br><br>For the remaining address components, the `Address` type provides the<br>`address_line_1` and `address_line_2` fields for free-form data entry.<br>These fields are free-form because the remaining address components have<br>too many variations around the world and typical software does not parse<br>these components. These fields enable users to enter anything they want.<br><br>Note that, in the current implementation, all other `Address` type fields are blank.<br>These include `address_line_3`, `sublocality_2`, `sublocality_3`,<br>`administrative_district_level_2`, `administrative_district_level_3`,<br>`first_name`, `last_name`, and `organization`.<br><br>When it comes to localization, the seller's language preferences<br>(see [Language preferences](https://developer.squareup.com/docs/locations-api#location-specific-and-seller-level-language-preferences))<br>are ignored for addresses. Even though Square products (such as Square Point of Sale<br>and the Seller Dashboard) mostly use a seller's language preference in<br>communication, when it comes to addresses, they will use English for a US address,<br>Japanese for an address in Japan, and so on. | getBillingAddress(): ?Address | setBillingAddress(?Address billingAddress): void |
| `buyerEmailAddress` | `?string` | Optional | The buyer's email address.<br><br>**Constraints**: *Maximum Length*: `255` | getBuyerEmailAddress(): ?string | setBuyerEmailAddress(?string buyerEmailAddress): void |
| `capabilities` | `?(string[])` | Optional | Actions that can be performed on this payment:<br><br>- `EDIT_AMOUNT_UP` - The payment amount can be edited up.<br>- `EDIT_AMOUNT_DOWN` - The payment amount can be edited down.<br>- `EDIT_TIP_AMOUNT_UP` - The tip amount can be edited up.<br>- `EDIT_TIP_AMOUNT_DOWN` - The tip amount can be edited down. | getCapabilities(): ?array | setCapabilities(?array capabilities): void |
| `cardDetails` | [`?CardPaymentDetails`](../../doc/models/card-payment-details.md) | Optional | Reflects the current status of a card payment. Contains only non-confidential information. | getCardDetails(): ?CardPaymentDetails | setCardDetails(?CardPaymentDetails cardDetails): void |
| `cashDetails` | [`?CashPaymentDetails`](../../doc/models/cash-payment-details.md) | Optional | Stores details about a cash payment. Contains only non-confidential information. For more information, see<br>[Take Cash Payments](https://developer.squareup.com/docs/payments-api/take-payments/cash-payments). | getCashDetails(): ?CashPaymentDetails | setCashDetails(?CashPaymentDetails cashDetails): void |
| `createdAt` | `?string` | Optional | The timestamp of when the payment was created, in RFC 3339 format.<br><br>**Constraints**: *Maximum Length*: `32` | getCreatedAt(): ?string | setCreatedAt(?string createdAt): void |
| `customerId` | `?string` | Optional | The [Customer](https://developer.squareup.com/reference/square_2021-08-18/objects/Customer) ID of the customer associated with the payment.<br><br>**Constraints**: *Maximum Length*: `191` | getCustomerId(): ?string | setCustomerId(?string customerId): void |
| `delayAction` | `?string` | Optional | The action to be applied to the payment when the `delay_duration` has elapsed. This field<br>is read-only.<br><br>Current values include `CANCEL`. | getDelayAction(): ?string | setDelayAction(?string delayAction): void |
| `delayDuration` | `?string` | Optional | The duration of time after the payment's creation when Square automatically applies the<br>`delay_action` to the payment. This automatic `delay_action` applies only to payments that<br>do not reach a terminal state (COMPLETED, CANCELED, or FAILED) before the `delay_duration`<br>time period.<br><br>This field is specified as a time duration, in RFC 3339 format.<br><br>Notes:<br>This feature is only supported for card payments.<br><br>Default:<br><br>- Card-present payments: "PT36H" (36 hours) from the creation time.<br>- Card-not-present payments: "P7D" (7 days) from the creation time. | getDelayDuration(): ?string | setDelayDuration(?string delayDuration): void |
| `delayedUntil` | `?string` | Optional | The read-only timestamp of when the `delay_action` is automatically applied,<br>in RFC 3339 format.<br><br>Note that this field is calculated by summing the payment's `delay_duration` and `created_at`<br>fields. The `created_at` field is generated by Square and might not exactly match the<br>time on your local machine. | getDelayedUntil(): ?string | setDelayedUntil(?string delayedUntil): void |
| `employeeId` | `?string` | Optional | An optional ID of the employee associated with taking the payment.<br><br>**Constraints**: *Maximum Length*: `192` | getEmployeeId(): ?string | setEmployeeId(?string employeeId): void |
| `externalDetails` | [`?ExternalPaymentDetails`](../../doc/models/external-payment-details.md) | Optional | Stores details about an external payment. Contains only non-confidential information.<br>For more information, see<br>[Take External Payments](https://developer.squareup.com/docs/payments-api/take-payments/external-payments). | getExternalDetails(): ?ExternalPaymentDetails | setExternalDetails(?ExternalPaymentDetails externalDetails): void |
| `id` | `?string` | Optional | A unique ID for the payment.<br><br>**Constraints**: *Maximum Length*: `192` | getId(): ?string | setId(?string id): void |
| `locationId` | `?string` | Optional | The ID of the location associated with the payment.<br><br>**Constraints**: *Maximum Length*: `50` | getLocationId(): ?string | setLocationId(?string locationId): void |
| `note` | `?string` | Optional | An optional note to include when creating a payment.<br><br>**Constraints**: *Maximum Length*: `500` | getNote(): ?string | setNote(?string note): void |
| `orderId` | `?string` | Optional | The ID of the order associated with the payment.<br><br>**Constraints**: *Maximum Length*: `192` | getOrderId(): ?string | setOrderId(?string orderId): void |
| `processingFee` | [`?(ProcessingFee[])`](../../doc/models/processing-fee.md) | Optional | The processing fees and fee adjustments assessed by Square for this payment. | getProcessingFee(): ?array | setProcessingFee(?array processingFee): void |
| `receiptNumber` | `?string` | Optional | The payment's receipt number.<br>The field is missing if a payment is canceled.<br><br>**Constraints**: *Maximum Length*: `4` | getReceiptNumber(): ?string | setReceiptNumber(?string receiptNumber): void |
| `receiptUrl` | `?string` | Optional | The URL for the payment's receipt.<br>The field is only populated for COMPLETED payments.<br><br>**Constraints**: *Maximum Length*: `255` | getReceiptUrl(): ?string | setReceiptUrl(?string receiptUrl): void |
| `referenceId` | `?string` | Optional | An optional ID that associates the payment with an entity in<br>another system.<br><br>**Constraints**: *Maximum Length*: `40` | getReferenceId(): ?string | setReferenceId(?string referenceId): void |
| `refundIds` | `?(string[])` | Optional | A list of `refund_id`s identifying refunds for the payment. | getRefundIds(): ?array | setRefundIds(?array refundIds): void |
| `refundedMoney` | [`?Money`](../../doc/models/money.md) | Optional | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getRefundedMoney(): ?Money | setRefundedMoney(?Money refundedMoney): void |
| `riskEvaluation` | [`?RiskEvaluation`](../../doc/models/risk-evaluation.md) | Optional | Represents fraud risk information for the associated payment.<br><br>When you take a payment through Square's Payments API (using the `CreatePayment`<br>endpoint), Square evaluates it and assigns a risk level to the payment. Sellers<br>can use this information to determine the course of action (for example,<br>provide the goods/services or refund the payment). | getRiskEvaluation(): ?RiskEvaluation | setRiskEvaluation(?RiskEvaluation riskEvaluation): void |
| `shippingAddress` | [`?Address`](../../doc/models/address.md) | Optional | Represents a postal address in a country. The address format is based<br>on an [open-source library from Google](https://github.com/google/libaddressinput). For more information,<br>see [AddressValidationMetadata](https://github.com/google/libaddressinput/wiki/AddressValidationMetadata).<br>This format has dedicated fields for four address components: postal code,<br>locality (city), administrative district (state, prefecture, or province), and<br>sublocality (town or village). These components have dedicated fields in the<br>`Address` object because software sometimes behaves differently based on them.<br>For example, sales tax software may charge different amounts of sales tax<br>based on the postal code, and some software is only available in<br>certain states due to compliance reasons.<br><br>For the remaining address components, the `Address` type provides the<br>`address_line_1` and `address_line_2` fields for free-form data entry.<br>These fields are free-form because the remaining address components have<br>too many variations around the world and typical software does not parse<br>these components. These fields enable users to enter anything they want.<br><br>Note that, in the current implementation, all other `Address` type fields are blank.<br>These include `address_line_3`, `sublocality_2`, `sublocality_3`,<br>`administrative_district_level_2`, `administrative_district_level_3`,<br>`first_name`, `last_name`, and `organization`.<br><br>When it comes to localization, the seller's language preferences<br>(see [Language preferences](https://developer.squareup.com/docs/locations-api#location-specific-and-seller-level-language-preferences))<br>are ignored for addresses. Even though Square products (such as Square Point of Sale<br>and the Seller Dashboard) mostly use a seller's language preference in<br>communication, when it comes to addresses, they will use English for a US address,<br>Japanese for an address in Japan, and so on. | getShippingAddress(): ?Address | setShippingAddress(?Address shippingAddress): void |
| `sourceType` | `?string` | Optional | The source type for this payment.<br><br>Current values include `CARD`, `BANK_ACCOUNT`, `WALLET`, `CASH`, or `EXTERNAL`.<br><br>**Constraints**: *Maximum Length*: `50` | getSourceType(): ?string | setSourceType(?string sourceType): void |
| `statementDescriptionIdentifier` | `?string` | Optional | Additional payment information that gets added to the customer's card statement<br>as part of the statement description.<br><br>Note that the `statement_description_identifier` might get truncated on the statement description<br>to fit the required information including the Square identifier (SQ *) and the name of the<br>seller taking the payment. | getStatementDescriptionIdentifier(): ?string | setStatementDescriptionIdentifier(?string statementDescriptionIdentifier): void |
| `status` | `?string` | Optional | Indicates whether the payment is APPROVED, PENDING, COMPLETED, CANCELED, or FAILED.<br><br>**Constraints**: *Maximum Length*: `50` | getStatus(): ?string | setStatus(?string status): void |
| `tipMoney` | [`?Money`](../../doc/models/money.md) | Optional | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getTipMoney(): ?Money | setTipMoney(?Money tipMoney): void |
| `totalMoney` | [`?Money`](../../doc/models/money.md) | Optional | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getTotalMoney(): ?Money | setTotalMoney(?Money totalMoney): void |
| `updatedAt` | `?string` | Optional | The timestamp of when the payment was last updated, in RFC 3339 format.<br><br>**Constraints**: *Maximum Length*: `32` | getUpdatedAt(): ?string | setUpdatedAt(?string updatedAt): void |
| `versionToken` | `?string` | Optional | Used for optimistic concurrency. This opaque token identifies a specific version of the<br>`Payment` object. | getVersionToken(): ?string | setVersionToken(?string versionToken): void |
| `walletDetails` | [`?DigitalWalletDetails`](../../doc/models/digital-wallet-details.md) | Optional | Additional details about `WALLET` type payments. Contains only non-confidential information. | getWalletDetails(): ?DigitalWalletDetails | setWalletDetails(?DigitalWalletDetails walletDetails): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\PaymentBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;
use SquareConnectAPILib\Models\Builders\BankAccountPaymentDetailsBuilder;
use SquareConnectAPILib\Models\Builders\ACHDetailsBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\AddressBuilder;

$payment = PaymentBuilder::init()
    ->amountMoney(
        MoneyBuilder::init()
            ->amount(186)
            ->currency('currency8')
            ->build()
    )
    ->appFeeMoney(
        MoneyBuilder::init()
            ->amount(106)
            ->currency('currency4')
            ->build()
    )
    ->approvedMoney(
        MoneyBuilder::init()
            ->amount(138)
            ->currency('currency2')
            ->build()
    )
    ->bankAccountDetails(
        BankAccountPaymentDetailsBuilder::init()
            ->accountOwnershipType('account_ownership_type8')
            ->achDetails(
                ACHDetailsBuilder::init()
                    ->accountNumberSuffix('account_number_suffix2')
                    ->accountType('account_type2')
                    ->routingNumber('routing_number0')
                    ->build()
            )
            ->bankName('bank_name4')
            ->country('country4')
            ->errors(
                [
                    ErrorBuilder::init(
                        'category8',
                        'code8'
                    )
                        ->detail('detail6')
                        ->field('field4')
                        ->build(),
                    ErrorBuilder::init(
                        'category8',
                        'code8'
                    )
                        ->detail('detail6')
                        ->field('field4')
                        ->build()
                ]
            )
            ->build()
    )
    ->billingAddress(
        AddressBuilder::init()
            ->addressLine1('address_line_12')
            ->addressLine2('address_line_28')
            ->addressLine3('address_line_34')
            ->administrativeDistrictLevel1('administrative_district_level_12')
            ->administrativeDistrictLevel2('administrative_district_level_26')
            ->build()
    )
    ->build();
```

