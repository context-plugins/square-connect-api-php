
# O Auth Scope Oauth 2 Enum

OAuth 2 scopes supported by the API

## Enumeration

`OAuthScopeOauth2Enum`

## Fields

| Name | Description |
|  --- | --- |
| `APPOINTMENTS_BUSINESS_SETTINGS_READ` | __HTTP Method__: `GET`<br><br>Grants read access to booking business settings. For example, to call the<br>ListTeamMemberBookingProfiles endpoint. |
| `APPOINTMENTS_READ` | __HTTP Method__: `GET`, `POST`<br><br>Grants read access to booking information. For example, to call the<br>RetrieveBooking endpoint. |
| `APPOINTMENTS_WRITE` | __HTTP Method__: `POST`, `PUT`, `DELETE`<br><br>Grants write access to booking information. For example, to call the CreateBooking endpoint. |
| `BANK_ACCOUNTS_READ` | __HTTP Method__: `GET`<br><br>Grants read access to bank account information associated with the targeted<br>Square account. For example, to call the Connect v1 ListBankAccounts endpoint. |
| `CASH_DRAWER_READ` | __HTTP Method__: `GET`<br><br>Grants read access to cash drawer shift information. For example, to call the<br>ListCashDrawerShifts endpoint. |
| `CUSTOMERS_READ` | __HTTP Method__: `GET`<br><br>Grants read access to customer information. For example, to call the<br>ListCustomers endpoint. |
| `CUSTOMERS_WRITE` | __HTTP Method__: `POST`, `PUT`, `DELETE`<br><br>Grants write access to customer information. For example, to create and update<br>customer profiles. |
| `DEVICE_CREDENTIAL_MANAGEMENT` | __HTTP Method__: `POST`, `GET`<br><br>Grants read/write access to device credentials information. For example, to<br>call the CreateDeviceCode endpoint. |
| `DISPUTES_READ` | __HTTP Method__: `GET`<br><br>Grants read access to dispute information. For example, to call the RetrieveDispute<br>endpoint. |
| `DISPUTES_WRITE` | __HTTP Method__: `POST`, `PUT`, `DELETE`<br><br>Grants write access to dispute information. For example, to call the SubmitEvidence<br>endpoint. |
| `EMPLOYEES_READ` | __HTTP Method__: `GET`<br><br>Grants read access to employee profile information. For example, to call the<br>Connect v1 Employees API. |
| `EMPLOYEES_WRITE` | __HTTP Method__: `POST`, `PUT`, `DELETE`<br><br>Grants write access to employee profile information. For example, to create<br>and modify employee profiles. |
| `GIFTCARDS_READ` | __HTTP Method__: `GET`, `POST`<br><br>Grants read access to gift card information. For example, to call the RetrieveGiftCard<br>endpoint. |
| `GIFTCARDS_WRITE` | __HTTP Method__: `POST`, `PUT`, `DELETE`<br><br>Grants write access to gift card information. For example, to call the CreateGiftCard<br>endpoint. |
| `INVENTORY_READ` | __HTTP Method__: `GET`<br><br>Grants read access to inventory information. For example, to call the<br>RetrieveInventoryCount endpoint. |
| `INVENTORY_WRITE` | __HTTP Method__:  `POST`, `PUT`, `DELETE`<br><br>Grants write access to inventory information. For example, to call the<br>BatchChangeInventory endpoint. |
| `INVOICES_READ` | __HTTP Method__: `GET`, `POST`<br><br>Grants read access to invoice information. For example, to call the ListInvoices endpoint. |
| `INVOICES_WRITE` | __HTTP Method__: `POST`, `PUT`, `DELETE`<br><br>Grants write access to invoice information. For example, to call the CreateInvoice endpoint. |
| `ITEMS_READ` | __HTTP Method__: `GET`<br><br>Grants read access to business and location information. For example, to<br>obtain a location ID for subsequent activity. |
| `ITEMS_WRITE` | __HTTP Method__: `POST`, `PUT`, `DELETE`<br><br>Grants write access to product catalog information. For example, to modify or<br>add to a product catalog. |
| `LOYALTY_READ` | __HTTP Method__: `GET`<br><br>Grants read access to loyalty information. For example, to call the<br>ListLoyaltyPrograms endpoint. |
| `LOYALTY_WRITE` | __HTTP Method__: `POST`, `PUT`, `DELETE`<br><br>Grants write access to loyalty information. For example, to call the<br>CreateLoyaltyAccount endpoint. |
| `MERCHANT_PROFILE_READ` | __HTTP Method__: `GET`<br><br>Grants read access to business and location information. For example, to<br>obtain a location ID for subsequent activity. |
| `MERCHANT_PROFILE_WRITE` | *Originally missing* |
| `ONLINE_STORE_SITE_READ` | __HTTP Method__: `GET`, `POST`<br><br>Read access to ECOM online store site details. |
| `ONLINE_STORE_SNIPPETS_READ` | __HTTP Method__: `GET`, `POST`<br><br>Read access to ECOM online store snippets on published websites. |
| `ONLINE_STORE_SNIPPETS_WRITE` | __HTTP Method__: `POST`, `PUT`, `DELETE`<br><br>Write access to ECOM online store snippets on published websites. |
| `ORDERS_READ` | __HTTP Method__: `GET`<br><br>Grants read access to order information. For example, to call the<br>BatchRetrieveOrders endpoint. |
| `ORDERS_WRITE` | __HTTP Method__: `POST`, `PUT`, `DELETE`<br><br>Grants write access to order information. For example, to call the<br>CreateCheckout endpoint. |
| `PAYMENTS_READ` | __HTTP Method__: `GET`<br><br>Grants read access to transaction and refund information. For example, to call<br>the RetrieveTransaction endpoint. |
| `PAYMENTS_WRITE` | __HTTP Method__: `POST`, `PUT`, `DELETE`<br><br>Grants write access to transaction and refunds information. For example, to<br>process payments with the Payments or Checkout API. |
| `PAYMENTS_WRITE_ADDITIONAL_RECIPIENTS` | __HTTP Method__: `POST`, `PUT`, `DELETE`<br><br>Allow third party applications to deduct a portion of each transaction amount.<br>__Required__ to use multiparty transaction functionality with the Payments<br>API. |
| `PAYMENTS_WRITE_IN_PERSON` | __HTTP Method__: `POST`, `PUT`, `DELETE`<br><br>Grants write access to payments and refunds information. For example, to<br>process in-person payments. |
| `PAYMENTS_WRITE_SHARED_ONFILE` | __HTTP Method__: `POST`, `PUT`, `DELETE`<br><br>Allows the developer to process payments on behalf of a seller using a shared on file payment method. |
| `SETTLEMENTS_READ` | __HTTP Method__: `GET`<br><br>Grants read access to settlement (deposit) information. For example, to call<br>the Connect v1 ListSettlements endpoint. |
| `SUBSCRIPTIONS_READ` | __HTTP Method__: `GET`, `POST`<br><br>Grants read access to subscription information. For example, to call the RetrieveSubscription<br>endpoint. |
| `SUBSCRIPTIONS_WRITE` | __HTTP Method__: `POST`, `PUT`, `DELETE`<br><br>Grants write access to subscription information. For example, to call the CreateSubscription<br>endpoint. |
| `TIMECARDS_READ` | __HTTP Method__: `GET`<br><br>Grants read access to employee timecard information. For example, to call the<br>Connect v2 SearchShifts endpoint. |
| `TIMECARDS_SETTINGS_READ` | __HTTP Method__: `GET`<br><br>Grants read access to employee timecard settings information. For example, to<br>call the GetBreakType endpoint. |
| `TIMECARDS_SETTINGS_WRITE` | __HTTP Method__: `POST`, `PUT`, `DELETE`<br><br>Grants write access to employee timecard settings information. For example, to<br>call the UpdateBreakType endpoint. |
| `TIMECARDS_WRITE` | __HTTP Method__: `POST`, `PUT`, `DELETE`<br><br>Grants write access to employee shift information. For example, to create<br>and modify employee shifts. |

## Example

```php
use SquareConnectAPILib\Models\OAuthScopeOauth2Enum;

$oAuthScopeOauth2 = OAuthScopeOauth2Enum::LOYALTY_WRITE;
```

