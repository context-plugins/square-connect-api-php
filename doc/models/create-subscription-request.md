
# Create Subscription Request

Defines parameters in a
[CreateSubscription](https://developer.squareup.com/reference/square_2021-08-18/subscriptions-api/create-subscription) endpoint request.

## Structure

`CreateSubscriptionRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `canceledDate` | `?string` | Optional | The date when the subscription should be canceled, in<br>YYYY-MM-DD format (for example, 2025-02-29). This overrides the plan configuration<br>if it comes before the date the subscription would otherwise end. | getCanceledDate(): ?string | setCanceledDate(?string canceledDate): void |
| `cardId` | `?string` | Optional | The ID of the [customer](https://developer.squareup.com/reference/square_2021-08-18/objects/Customer) [card](https://developer.squareup.com/reference/square_2021-08-18/objects/Card) to charge.<br>If not specified, Square sends an invoice via email. For an example to<br>create a customer and add a card on file, see [Subscriptions Walkthrough](https://developer.squareup.com/docs/subscriptions-api/walkthrough). | getCardId(): ?string | setCardId(?string cardId): void |
| `customerId` | `string` | Required | The ID of the [customer](https://developer.squareup.com/reference/square_2021-08-18/objects/Customer) profile.<br><br>**Constraints**: *Minimum Length*: `1` | getCustomerId(): string | setCustomerId(string customerId): void |
| `idempotencyKey` | `?string` | Optional | A unique string that identifies this `CreateSubscription` request.<br>If you do not provide a unique string (or provide an empty string as the value),<br>the endpoint treats each request as independent.<br><br>For more information, see [Idempotency keys](https://developer.squareup.com/docs/working-with-apis/idempotency). | getIdempotencyKey(): ?string | setIdempotencyKey(?string idempotencyKey): void |
| `locationId` | `string` | Required | The ID of the location the subscription is associated with.<br><br>**Constraints**: *Minimum Length*: `1` | getLocationId(): string | setLocationId(string locationId): void |
| `planId` | `string` | Required | The ID of the subscription plan created using the Catalog API.<br>For more information, see<br>[Set Up and Manage a Subscription Plan](https://developer.squareup.com/docs/subscriptions-api/setup-plan) and<br>[Subscriptions Walkthrough](https://developer.squareup.com/docs/subscriptions-api/walkthrough).<br><br>**Constraints**: *Minimum Length*: `1` | getPlanId(): string | setPlanId(string planId): void |
| `priceOverrideMoney` | [`?Money`](../../doc/models/money.md) | Optional | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getPriceOverrideMoney(): ?Money | setPriceOverrideMoney(?Money priceOverrideMoney): void |
| `startDate` | `?string` | Optional | The start date of the subscription, in YYYY-MM-DD format. For example,<br>2013-01-15. If the start date is left empty, the subscription begins<br>immediately. | getStartDate(): ?string | setStartDate(?string startDate): void |
| `taxPercentage` | `?string` | Optional | The tax to add when billing the subscription.<br>The percentage is expressed in decimal form, using a `'.'` as the decimal<br>separator and without a `'%'` sign. For example, a value of 7.5<br>corresponds to 7.5%.<br><br>**Constraints**: *Maximum Length*: `10` | getTaxPercentage(): ?string | setTaxPercentage(?string taxPercentage): void |
| `timezone` | `?string` | Optional | The timezone that is used in date calculations for the subscription. If unset, defaults to<br>the location timezone. If a timezone is not configured for the location, defaults to "America/New_York".<br>Format: the IANA Timezone Database identifier for the location timezone. For<br>a list of time zones, see [List of tz database time zones](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones). | getTimezone(): ?string | setTimezone(?string timezone): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CreateSubscriptionRequestBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;

$createSubscriptionRequest = CreateSubscriptionRequestBuilder::init(
    'customer_id4',
    'location_id0',
    'plan_id8'
)
    ->canceledDate('canceled_date0')
    ->cardId('card_id2')
    ->idempotencyKey('idempotency_key2')
    ->priceOverrideMoney(
        MoneyBuilder::init()
            ->amount(42)
            ->currency('currency8')
            ->build()
    )
    ->startDate('start_date0')
    ->build();
```

