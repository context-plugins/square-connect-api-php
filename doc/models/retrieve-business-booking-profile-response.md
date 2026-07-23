
# Retrieve Business Booking Profile Response

## Structure

`RetrieveBusinessBookingProfileResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `businessBookingProfile` | [`?BusinessBookingProfile`](../../doc/models/business-booking-profile.md) | Optional | - | getBusinessBookingProfile(): ?BusinessBookingProfile | setBusinessBookingProfile(?BusinessBookingProfile businessBookingProfile): void |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\RetrieveBusinessBookingProfileResponseBuilder;
use SquareConnectAPILib\Models\Builders\BusinessBookingProfileBuilder;
use SquareConnectAPILib\Models\Builders\BusinessAppointmentSettingsBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;

$retrieveBusinessBookingProfileResponse = RetrieveBusinessBookingProfileResponseBuilder::init()
    ->businessBookingProfile(
        BusinessBookingProfileBuilder::init()
            ->allowUserCancel(true)
            ->bookingEnabled(true)
            ->bookingPolicy('ACCEPT_ALL')
            ->businessAppointmentSettings(
                BusinessAppointmentSettingsBuilder::init()
                    ->alignmentTime('HALF_HOURLY')
                    ->anyTeamMemberBookingEnabled(true)
                    ->cancellationFeeMoney(
                        MoneyBuilder::init()
                            ->amount(72)
                            ->currency('USD')
                            ->build()
                    )
                    ->cancellationPolicy('CUSTOM_POLICY')
                    ->cancellationPolicyText('cancellation_policy_text2')
                    ->locationTypes(
                        [
                            'BUSINESS_LOCATION'
                        ]
                    )
                    ->maxBookingLeadTimeSeconds(31536000)
                    ->minBookingLeadTimeSeconds(0)
                    ->multipleServiceBookingEnabled(true)
                    ->skipBookingFlowStaffSelection(false)
                    ->build()
            )
            ->createdAt('2020-09-10T21:40:38Z')
            ->customerTimezoneChoice('CUSTOMER_CHOICE')
            ->sellerId('MLJQYZZRM0D3Y')
            ->build()
    )
    ->errors(
        []
    )
    ->build();
```

