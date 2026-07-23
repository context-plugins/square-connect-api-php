
# Create Checkout Request

Defines the parameters that can be included in the body of
a request to the `CreateCheckout` endpoint.

## Structure

`CreateCheckoutRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `additionalRecipients` | [`?(ChargeRequestAdditionalRecipient[])`](../../doc/models/charge-request-additional-recipient.md) | Optional | The basic primitive of a multi-party transaction. The value is optional.<br>The transaction facilitated by you can be split from here.<br><br>If you provide this value, the `amount_money` value in your `additional_recipients` field<br>cannot be more than 90% of the `total_money` calculated by Square for your order.<br>The `location_id` must be a valid seller location where the checkout is occurring.<br><br>This field requires `PAYMENTS_WRITE_ADDITIONAL_RECIPIENTS` OAuth permission.<br><br>This field is currently not supported in the Square Sandbox. | getAdditionalRecipients(): ?array | setAdditionalRecipients(?array additionalRecipients): void |
| `askForShippingAddress` | `?bool` | Optional | If `true`, Square Checkout collects shipping information on your behalf and stores<br>that information with the transaction information in the Square Seller Dashboard.<br><br>Default: `false`. | getAskForShippingAddress(): ?bool | setAskForShippingAddress(?bool askForShippingAddress): void |
| `idempotencyKey` | `string` | Required | A unique string that identifies this checkout among others you have created. It can be<br>any valid string but must be unique for every order sent to Square Checkout for a given location ID.<br><br>The idempotency key is used to avoid processing the same order more than once. If you are<br>unsure whether a particular checkout was created successfully, you can attempt it again with<br>the same idempotency key and all the same other parameters without worrying about creating duplicates.<br><br>You should use a random number/string generator native to the language<br>you are working in to generate strings for your idempotency keys.<br><br>For more information, see [Idempotency](https://developer.squareup.com/docs/working-with-apis/idempotency).<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `192` | getIdempotencyKey(): string | setIdempotencyKey(string idempotencyKey): void |
| `merchantSupportEmail` | `?string` | Optional | The email address to display on the Square Checkout confirmation page<br>and confirmation email that the buyer can use to contact the seller.<br><br>If this value is not set, the confirmation page and email display the<br>primary email address associated with the seller's Square account.<br><br>Default: none; only exists if explicitly set.<br><br>**Constraints**: *Maximum Length*: `254` | getMerchantSupportEmail(): ?string | setMerchantSupportEmail(?string merchantSupportEmail): void |
| `note` | `?string` | Optional | An optional note to associate with the `checkout` object.<br><br>This value cannot exceed 60 characters.<br><br>**Constraints**: *Maximum Length*: `60` | getNote(): ?string | setNote(?string note): void |
| `order` | [`CreateOrderRequest`](../../doc/models/create-order-request.md) | Required | - | getOrder(): CreateOrderRequest | setOrder(CreateOrderRequest order): void |
| `prePopulateBuyerEmail` | `?string` | Optional | If provided, the buyer's email is prepopulated on the checkout page<br>as an editable text field.<br><br>Default: none; only exists if explicitly set.<br><br>**Constraints**: *Maximum Length*: `254` | getPrePopulateBuyerEmail(): ?string | setPrePopulateBuyerEmail(?string prePopulateBuyerEmail): void |
| `prePopulateShippingAddress` | [`?Address`](../../doc/models/address.md) | Optional | Represents a postal address in a country. The address format is based<br>on an [open-source library from Google](https://github.com/google/libaddressinput). For more information,<br>see [AddressValidationMetadata](https://github.com/google/libaddressinput/wiki/AddressValidationMetadata).<br>This format has dedicated fields for four address components: postal code,<br>locality (city), administrative district (state, prefecture, or province), and<br>sublocality (town or village). These components have dedicated fields in the<br>`Address` object because software sometimes behaves differently based on them.<br>For example, sales tax software may charge different amounts of sales tax<br>based on the postal code, and some software is only available in<br>certain states due to compliance reasons.<br><br>For the remaining address components, the `Address` type provides the<br>`address_line_1` and `address_line_2` fields for free-form data entry.<br>These fields are free-form because the remaining address components have<br>too many variations around the world and typical software does not parse<br>these components. These fields enable users to enter anything they want.<br><br>Note that, in the current implementation, all other `Address` type fields are blank.<br>These include `address_line_3`, `sublocality_2`, `sublocality_3`,<br>`administrative_district_level_2`, `administrative_district_level_3`,<br>`first_name`, `last_name`, and `organization`.<br><br>When it comes to localization, the seller's language preferences<br>(see [Language preferences](https://developer.squareup.com/docs/locations-api#location-specific-and-seller-level-language-preferences))<br>are ignored for addresses. Even though Square products (such as Square Point of Sale<br>and the Seller Dashboard) mostly use a seller's language preference in<br>communication, when it comes to addresses, they will use English for a US address,<br>Japanese for an address in Japan, and so on. | getPrePopulateShippingAddress(): ?Address | setPrePopulateShippingAddress(?Address prePopulateShippingAddress): void |
| `redirectUrl` | `?string` | Optional | The URL to redirect to after the checkout is completed with `checkoutId`,<br>`transactionId`, and `referenceId` appended as URL parameters. For example,<br>if the provided redirect URL is `http://www.example.com/order-complete`, a<br>successful transaction redirects the customer to:<br><br><pre><code>http://www.example.com/order-complete?checkoutId=xxxxxx&amp;referenceId=xxxxxx&amp;transactionId=xxxxxx</code></pre><br>If you do not provide a redirect URL, Square Checkout displays an order<br>confirmation page on your behalf; however, it is strongly recommended that<br>you provide a redirect URL so you can verify the transaction results and<br>finalize the order through your existing/normal confirmation workflow.<br><br>Default: none; only exists if explicitly set.<br><br>**Constraints**: *Maximum Length*: `800` | getRedirectUrl(): ?string | setRedirectUrl(?string redirectUrl): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CreateCheckoutRequestBuilder;
use SquareConnectAPILib\Models\Builders\CreateOrderRequestBuilder;
use SquareConnectAPILib\Models\Builders\OrderBuilder;
use SquareConnectAPILib\Models\Builders\OrderLineItemDiscountBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;
use SquareConnectAPILib\Models\Builders\OrderFulfillmentBuilder;
use SquareConnectAPILib\Models\Builders\OrderFulfillmentPickupDetailsBuilder;
use SquareConnectAPILib\Models\Builders\OrderFulfillmentPickupDetailsCurbsidePickupDetailsBuilder;
use SquareConnectAPILib\Models\Builders\OrderFulfillmentShipmentDetailsBuilder;
use SquareConnectAPILib\Models\Builders\ChargeRequestAdditionalRecipientBuilder;

$createCheckoutRequest = CreateCheckoutRequestBuilder::init(
    'idempotency_key4',
    CreateOrderRequestBuilder::init()
        ->idempotencyKey('idempotency_key2')
        ->order(
            OrderBuilder::init(
                'location_id0'
            )
                ->closedAt('closed_at8')
                ->createdAt('created_at4')
                ->customerId('customer_id4')
                ->discounts(
                    [
                        OrderLineItemDiscountBuilder::init()
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
                            ->catalogObjectId('catalog_object_id8')
                            ->catalogVersion(84)
                            ->metadata(
                                [
                                    'key0' => 'metadata1'
                                ]
                            )
                            ->build(),
                        OrderLineItemDiscountBuilder::init()
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
                            ->catalogObjectId('catalog_object_id8')
                            ->catalogVersion(84)
                            ->metadata(
                                [
                                    'key0' => 'metadata1'
                                ]
                            )
                            ->build()
                    ]
                )
                ->fulfillments(
                    [
                        OrderFulfillmentBuilder::init()
                            ->metadata(
                                [
                                    'key0' => 'metadata9'
                                ]
                            )
                            ->pickupDetails(
                                OrderFulfillmentPickupDetailsBuilder::init()
                                    ->acceptedAt('accepted_at2')
                                    ->autoCompleteDuration('auto_complete_duration2')
                                    ->cancelReason('cancel_reason4')
                                    ->canceledAt('canceled_at4')
                                    ->curbsidePickupDetails(
                                        OrderFulfillmentPickupDetailsCurbsidePickupDetailsBuilder::init()
                                            ->buyerArrivedAt('buyer_arrived_at8')
                                            ->curbsideDetails('curbside_details2')
                                            ->build()
                                    )
                                    ->build()
                            )
                            ->shipmentDetails(
                                OrderFulfillmentShipmentDetailsBuilder::init()
                                    ->cancelReason('cancel_reason6')
                                    ->canceledAt('canceled_at4')
                                    ->carrier('carrier0')
                                    ->expectedShippedAt('expected_shipped_at2')
                                    ->failedAt('failed_at2')
                                    ->build()
                            )
                            ->state('state0')
                            ->type('type6')
                            ->build(),
                        OrderFulfillmentBuilder::init()
                            ->metadata(
                                [
                                    'key0' => 'metadata9'
                                ]
                            )
                            ->pickupDetails(
                                OrderFulfillmentPickupDetailsBuilder::init()
                                    ->acceptedAt('accepted_at2')
                                    ->autoCompleteDuration('auto_complete_duration2')
                                    ->cancelReason('cancel_reason4')
                                    ->canceledAt('canceled_at4')
                                    ->curbsidePickupDetails(
                                        OrderFulfillmentPickupDetailsCurbsidePickupDetailsBuilder::init()
                                            ->buyerArrivedAt('buyer_arrived_at8')
                                            ->curbsideDetails('curbside_details2')
                                            ->build()
                                    )
                                    ->build()
                            )
                            ->shipmentDetails(
                                OrderFulfillmentShipmentDetailsBuilder::init()
                                    ->cancelReason('cancel_reason6')
                                    ->canceledAt('canceled_at4')
                                    ->carrier('carrier0')
                                    ->expectedShippedAt('expected_shipped_at2')
                                    ->failedAt('failed_at2')
                                    ->build()
                            )
                            ->state('state0')
                            ->type('type6')
                            ->build()
                    ]
                )
                ->build()
        )
        ->build()
)
    ->additionalRecipients(
        [
            ChargeRequestAdditionalRecipientBuilder::init(
                MoneyBuilder::init()
                    ->amount(186)
                    ->currency('currency8')
                    ->build(),
                'description6',
                'location_id0'
            )->build(),
            ChargeRequestAdditionalRecipientBuilder::init(
                MoneyBuilder::init()
                    ->amount(186)
                    ->currency('currency8')
                    ->build(),
                'description6',
                'location_id0'
            )->build()
        ]
    )
    ->askForShippingAddress(false)
    ->merchantSupportEmail('merchant_support_email6')
    ->note('note4')
    ->prePopulateBuyerEmail('pre_populate_buyer_email6')
    ->build();
```

