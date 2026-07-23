
# Business Booking Profile

## Structure

`BusinessBookingProfile`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `allowUserCancel` | `?bool` | Optional | Indicates whether customers can cancel or reschedule their own bookings (`true`) or not (`false`). | getAllowUserCancel(): ?bool | setAllowUserCancel(?bool allowUserCancel): void |
| `bookingEnabled` | `?bool` | Optional | Indicates whether the seller is open for booking. | getBookingEnabled(): ?bool | setBookingEnabled(?bool bookingEnabled): void |
| `bookingPolicy` | `?string` | Optional | The policy for the seller to automatically accept booking requests (`ACCEPT_ALL`) or not (`REQUIRES_ACCEPTANCE`). | getBookingPolicy(): ?string | setBookingPolicy(?string bookingPolicy): void |
| `businessAppointmentSettings` | [`?BusinessAppointmentSettings`](../../doc/models/business-appointment-settings.md) | Optional | The service appointment settings, including where and how the service is provided. | getBusinessAppointmentSettings(): ?BusinessAppointmentSettings | setBusinessAppointmentSettings(?BusinessAppointmentSettings businessAppointmentSettings): void |
| `createdAt` | `?string` | Optional | The RFC 3339 timestamp specifying the booking's creation time. | getCreatedAt(): ?string | setCreatedAt(?string createdAt): void |
| `customerTimezoneChoice` | `?string` | Optional | The choice of customer's time zone information of a booking.<br>The Square online booking site and all notifications to customers uses either the seller location’s time zone<br>or the time zone the customer chooses at booking. | getCustomerTimezoneChoice(): ?string | setCustomerTimezoneChoice(?string customerTimezoneChoice): void |
| `sellerId` | `?string` | Optional | The ID of the seller, obtainable using the Merchants API. | getSellerId(): ?string | setSellerId(?string sellerId): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\BusinessBookingProfileBuilder;
use SquareConnectAPILib\Models\Builders\BusinessAppointmentSettingsBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;

$businessBookingProfile = BusinessBookingProfileBuilder::init()
    ->allowUserCancel(false)
    ->bookingEnabled(false)
    ->bookingPolicy('booking_policy2')
    ->businessAppointmentSettings(
        BusinessAppointmentSettingsBuilder::init()
            ->alignmentTime('alignment_time0')
            ->anyTeamMemberBookingEnabled(false)
            ->cancellationFeeMoney(
                MoneyBuilder::init()
                    ->amount(72)
                    ->currency('currency8')
                    ->build()
            )
            ->cancellationPolicy('cancellation_policy6')
            ->cancellationPolicyText('cancellation_policy_text2')
            ->build()
    )
    ->createdAt('created_at0')
    ->build();
```

